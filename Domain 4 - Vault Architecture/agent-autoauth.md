### Documentation Referred:

https://www.vaultproject.io/docs/agent/autoauth

###  AppRole Related Configurations
```sh
vault auth enable approle
vault write auth/approle/role/vaultagent token_policies="agent-policy"
vault read auth/approle/role/vaultagent/role-id
vault write -f auth/approle/role/vaultagent/secret-id
```
### ACL Policy:
```sh
path "auth/token/create" {
  capabilities = ["update"]
}

Vault Agent Configuration File:

exit_after_auth = false
pid_file = "./pidfile"

auto_auth {
   method "approle" {
       mount_path = "auth/approle"
       config = {
           role_id_file_path = "/tmp/role-id"
           secret_id_file_path = "/tmp/secret-id"
           remove_secret_id_file_after_reading = false
       }
   }

   sink "file" {
       config = {
           path = "/tmp/token"
       }
   }
}

vault {
   address = "http://127.0.0.1:8200"
}
```
### Store the Role-ID and Secret -ID under /tmp/role-id and /tmp-secret-id location
```sh
nano /tmp/role-id
nano /tmp/secret-id
```
### Start the Vault Agent
```sh
vault agent -config=agent.hcl
```

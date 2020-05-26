### Agent Configuration File:
```sh
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

cache {
  use_auto_auth_token = true
}

listener "tcp" {
   address = "127.0.0.1:8007"
   tls_disable = true
}


vault {
   address = "http://127.0.0.1:8200"
}
```
### Exporting Environment Variable:
```sh
export VAULT_AGENT_ADDR="http://127.0.0.1:8007"
```
### Miscellaneous commands used:
```sh
VAULT_TOKEN=$(cat /tmp/token) vault token create
printenv
unset VAULT_AGENT_ADDR
export VAULT_ADDR='http://127.0.0.1:8200'
```

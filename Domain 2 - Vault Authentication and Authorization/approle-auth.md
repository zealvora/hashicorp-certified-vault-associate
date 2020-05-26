### ACL Policy:
```sh
path "secret/*" {
  capabilities = ["create","read","update","delete"]
}
```
### Create a new Role with associated policy:
```sh
vault write auth/approle/role/jenkins token_policies="jenkins-role-policy"
```
### Fetch Information About Role:
```sh
vault read auth/approle/role/jenkins
```
### Fetch the Role ID
```sh
vault read auth/approle/role/jenkins/role-id
```
### Fetch the Role ID
```sh
vault write -f auth/approle/role/jenkins/secret-id
```
### Authenticate with AppRole
```sh
vault write auth/approle/login role_id="YOUR-ROLE-ID" secret_id="YOUR-SECRET-ID"
```

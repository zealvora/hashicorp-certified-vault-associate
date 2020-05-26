### ACL Policy - sample-policy
```sh
path "secret/*" {
  capabilities = ["list","read"]
}

path "auth/token/lookup-self" {
   capabilities = ["read"]
   }
```
### Commands that were used in the video:
```sh
vault login -method=userpass username=demouser password=password
vault token lookup
vault login [root-token-identifier]
```

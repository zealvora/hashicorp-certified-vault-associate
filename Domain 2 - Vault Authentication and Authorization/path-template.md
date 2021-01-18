```sh
path "secret/data/{{identity.entity.name}}/*" {
    capabilities = ["create", "update", "read"]
}
```
```sh
path "secret/metadata" {
    capabilities = ["list"]
}
```
```sh
vault login -method=userpass username="alice" password="password"

vault kv get secret/alice-user/appcreds
```

### Base Policy Used For Entities and Users:
```sh
path "secret/*" {
  capabilities = ["read"]
}
```

### Policy Names:
```sh
entity-policy
bob-policy
bsmith-policy
```
### Login to bob and bsmith user
```sh
vault login -method=userpass username=bob password=password
vault login -method=userpass username=bsmith password=password
```

### Policy for the demo user
```sh
path "auth/token/*" {
  capabilities = ["create", "read","update"]
}
```
###  Commands used during the video:
```sh
vault login -method=userpass username=demouser password=password
vault token create
vault token create --tl=60
vault token lookup [TOKEN]
vault token renew -increment=99999m [TOKEN]
```
### Token Related Configuration:
```sh
vault read sys/auth/token/tune
```

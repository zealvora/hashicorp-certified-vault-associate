### Capabilities Assigned to demouser:
```sh
path "auth/token/create" {
  capabilities = ["create","read","update","sudo"]
}

path "auth/token/lookup" {
  capabilities = ["create","read","update"]
}
```
### Commands used to create orphan token:
```sh
vault token create -orphan
```
### Performing a lookup for the token:
```sh
vault token lookup s.eiaBtk4aF7mikTZ6a6kc5sBq
```

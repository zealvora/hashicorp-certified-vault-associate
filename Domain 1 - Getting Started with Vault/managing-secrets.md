### Create multiple versions of secret
```sh
vault kv put secret/second-secret user=admin01
vault kv put secret/second-secret user=admin02
vault kv put secret/second-secret user=admin03
```
### Read Secret:
```sh
vault kv get secret/second-secret
```
### Read specific version of secret
```sh
vault kv get -version=2 secret/second-secret
```
### Delete specific version of secret
```sh
vault kv delete -versions=2 secret/second-secret
```
### Undelete version of secret
```sh
vault kv undelete -versions=2 secret/second-secret
```
### Permanently delete version of secret:
```sh
vault kv destroy -versions=2 secret/second-secret
```
### Delete the secret
```sh
vault kv metadata delete secret/second-secret
```

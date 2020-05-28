### API Documentation Referred:

https://www.vaultproject.io/api-docs/secret/kv/kv-v2

### Reading the current token:
```sh
vault print token
```
### Read the firstsecret
```sh
curl --header "X-Vault-Token: s.D4mEpn77EhyLvDOrAy2egr8g" https://127.0.0.1:8200/v1/secret/data/firstsecret?version=1
```
### Create a new secret:
```sh
curl --header "X-Vault-Token: s.D4mEpn77EhyLvDOrAy2egr8g" --request POST --data @payload.json http://127.0.0.1:8200/v1/secret/data/api-secret
```
### payload.json
```sh
{
  "data": {
  "course": "vault-associate",
  "instructor": "zeal"
  }
}
```

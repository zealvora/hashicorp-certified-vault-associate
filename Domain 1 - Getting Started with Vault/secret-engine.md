### Documentation Referred in the Video:

https://www.vaultproject.io/docs/secrets

### Enable a new KV Secret Engine:
```sh
vault secrets enable -path=demopath -version=2 kv
vault secrets disable demopath/
```

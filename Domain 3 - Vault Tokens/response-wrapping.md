### Creating a response wrapped token:
```sh
vault token create -wrap-ttl=600
```
### Unwrap token from wrap:
```sh
vault unwrap [wrapping-token]
``

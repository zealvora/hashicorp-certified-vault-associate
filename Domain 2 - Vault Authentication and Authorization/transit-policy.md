```sh
path "transit/encrypt/demo-key" {
   capabilities = [ "update" ]
}

path "transit/decrypt/demo-key" {
   capabilities = [ "update" ]
}

path "transit/keys" {
   capabilities = [ "list" ]
}

path "transit/keys/demo-key" {
   capabilities = [ "read" ]
}
```

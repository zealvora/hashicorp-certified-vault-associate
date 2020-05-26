### demo.hcl
```sh
storage "file" {
  path = "/root/vault-data"
}

listener "tcp" {
  address     = "0.0.0.0:8200"
  tls_disable = 1
}

ui = "true"
```
###  Verify if Vault is listening on the current address
```sh
netstat -ntlp
```

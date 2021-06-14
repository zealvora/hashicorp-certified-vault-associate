
#### Base Configuration File:

```sh
listener "tcp" {
  address     = "0.0.0.0:8200"
  tls_disable = 1
}

ui=true

storage "file" {
  path  = "./new-vault-data"
}

seal "awskms" {
  region     = "us-east-1"
  access_key = "YOUR-ACCESS-KEY"
  secret_key = "YOUR-SECRET-KEY"
  kms_key_id = "YOUR-KMS-ID"
}
```

#### CLI Commands
```sh
vault server config unseal.hcl
vault operator init
```

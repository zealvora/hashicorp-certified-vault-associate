### Documentation Referred in the Video:

https://www.vaultproject.io/docs/configuration

https://www.vaultproject.io/docs/configuration/storage/filesystem

### Step 1 - Vault Configuration File
```sh
storage "file" {
  path  = "/root/vault-data"
}

listener "tcp" {
 address     = "127.0.0.1:8200"
 tls_disable = 1
}
```
###  Step 2 - Start Vault Server with Configuration File
```sh
vault server - config demo.hcl
```
###  Step 3 - Initialize the Vault
```sh
export VAULT_ADDR='http://127.0.0.1:8200'
vault operator init
```
###  Step 4 - Unseal the vault
```sh
vault operator unseal
```

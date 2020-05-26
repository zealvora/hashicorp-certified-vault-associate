### Vault Policies used in the video:

Commands used in the video:
```sh
vault login -method=userpass username=admin password=password
vault secrets list
vault kv get secret/firstsecret
vault kv get secret/supersecret
```

### Final ACL Policy:
```sh
path "sys/mounts" {
  capabilities = ["read"]
}

path "sys/policies/acl" {
  capabilities = ["read","list"]
}

path "secret/*" {
  capabilities = ["read"]
}

path "secret/+/supersecret" {
  capabilities = ["deny"]
}
```

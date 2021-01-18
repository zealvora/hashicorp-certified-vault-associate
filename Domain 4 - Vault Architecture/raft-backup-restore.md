### Backup and Snapshot:

```sh
vault kv put secret/sensitive dbadmin=dbpasswd
vault kv get secret/sensitive
```

#### Take Backup:
```sh
vault operator raft snapshot save demo.snapshot

vault kv delete secret/sensitive
```
#### Restore:
```sh
vault operator raft snapshot restore demo.snapshot

vault kv delete secret/sensitive
```

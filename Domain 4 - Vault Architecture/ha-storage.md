## Server 1:
```sh
cd /root
mkdir /root/storage
mkdir /root/raft-node1/
```
```sh
nano config-node01.hcl
```
```sh
storage "file" {
  path    = "/root/storage/"
  node_id = "node1"
}

ha_storage "raft" {
  path    = "/root/raft-node1/"
  node_id = "node1"
}

listener "tcp" {
  address = "127.0.0.1:8210"
  cluster_address = "127.0.0.1:8211"
  tls_disable = true
}

disable_mlock = true
api_addr = "http://127.0.0.1:8210"
cluster_addr = "http://127.0.0.1:8211"
```
```sh
vault server -config=config-node01.hcl
```
#### Different Terminal:
```sh
export VAULT_ADDR='http://127.0.0.1:8210'
vault operator init -key-shares=1 -key-threshold=1 > key.txt
cat key.txt
vault operator unseal
vault login [ROOT-TOKEN]
vault operator raft list-peers
```

## Server 2:
```sh
cd /root
mkdir /root/raft-node2/
```
```sh
nano config-node02.hcl
```
```sh
storage "file" {
  path    = "/root/storage/"
  node_id = "node2"
}

ha_storage "raft" {
  path    = "/root/raft-node2/"
  node_id = "node2"
}

listener "tcp" {
  address = "127.0.0.1:8220"
  cluster_address = "127.0.0.1:8221"
  tls_disable = true
}

disable_mlock = true
api_addr = "http://127.0.0.1:8220"
cluster_addr = "http://127.0.0.1:8221"
```
```sh
vault server -config=config-node02.hcl
```
#### Different Terminal:

```sh
export VAULT_ADDR='http://127.0.0.1:8220'
vault operator unseal
vault operator raft join
vault status
vault login [ROOT-TOKEN]
vault operator raft list-peers
```

## Server 3:
```sh
mkdir /root/raft-node3/
```
```sh
nano /root/config-node03.hcl
```
```sh
ha_storage "raft" {
  path    = "/root/raft-node3/"
  node_id = "node3"
}

storage "file" {
    path = "/root/storage"
}

listener "tcp" {
  address = "127.0.0.1:8230"
  cluster_address = "127.0.0.1:8231"
  tls_disable = true
}

disable_mlock = true
api_addr = "http://127.0.0.1:8230"
cluster_addr = "http://127.0.0.1:8231"
```
```sh
vault server -config=/root/config-node03.hcl
```

#### Different Terminal:
```sh
export VAULT_ADDR='http://127.0.0.1:8230'
vault operator unseal
vault operator raft join
vault status
vault login [ROOT-TOKEN]
vault operator raft list-peers
```
```sh
export VAULT_ADDR='http://127.0.0.1:8210'
vault operator step-down
```

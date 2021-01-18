
#### Step 1 - Verify the generic token duration:
```sh
vault token create -policy=default
```
#### Step 2 - Modify the Defaults:
```sh
vault read sys/mounts/auth/token/tune
vault write sys/mounts/auth/token/tune default_lease_ttl=5m max_lease_ttl=10m
vault token create -policy=default
```
#### Step 3 - Set Different TTL for Auth Method:

Change default TTL and Maximum TTL from GUI
```sh
vault login -method=userpass username=admin password=password
vault token create -policy=default
```

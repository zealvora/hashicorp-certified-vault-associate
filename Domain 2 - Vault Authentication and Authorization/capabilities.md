```sh
vault login -method=userpass username=demouser password=password
vault token capabilities sys/
vault login [ROOT-TOKEN]
vault token capabilities [YOUR-TOKEN] sys/
```

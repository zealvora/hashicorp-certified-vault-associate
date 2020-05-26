### Documentation for Vault Downloads File:

https://www.vaultproject.io/downloads

### To check architecture for MAC and Linux:
```sh
arch
```

### Commands used for Installing Vault in Linux
```sh
yum -y install wget unzip
wget https://releases.hashicorp.com/vault/1.4.1/vault_1.4.1_linux_amd64.zip
unzip vault_1.4.1_linux_amd64.zip
echo $PATH
mv vault /usr/local/bin
```

For MAC users, the command 1,2,3 can be achieved with GUI via your browsers, and command number 4 and 5 remains to be the same as Linux.

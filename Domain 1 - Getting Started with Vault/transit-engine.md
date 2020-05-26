### Encrypting Data
```sh
vault write transit/encrypt/demo-key plaintext=IlRoaXMgaXMgb3VyIGVuY29kZWQgdGV4dCI=
```
### Decrypting Data
```sh
vault write transit/decrypt/demo-key ciphertext=[YOUR-CIPHERTEXT-HERE]
```
### Website Used During Video:

https://www.base64decode.org/

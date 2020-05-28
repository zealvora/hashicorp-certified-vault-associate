### Pages referred in the video:

Documentation:
https://www.vaultproject.io/docs/audit/file
https://www.vaultproject.io/api-docs/system/audit-hash
https://jsonformatter.curiousconcept.com/

### Sample Payload:
```sh
{
  "input": "s.o3QnlCsU9d6peCwkDs25fHys"
}
```
### Commands used:
```sh
vault audit list
vault audit enable file file_path=vault-audit.log
vault audit enable -path="audit_path" file file_path=/var/log/vault-audit.log
cat /var/log/audit/vault-audit.log | jq
```
### CURL Request:
```sh
curl --header "X-Vault-Token: s.o3QnlCsU9d6peCwkDs25fHys" --request POST --data @audit.json http://127.0.0.1:8200/v1/sys/audit-hash/file
```

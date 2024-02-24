Command to get the last password change details of a specific user. dedup is used to remove similar events.

```spl
index="<index here>" sourcetype="< add type>" source="activedirectory users" <user name>
| dedup pwdLastSet
| table pwdLastSet, email, sourcetype
| rename pwdLastSet as "Password Last Change Date", email as "User"
| sort -_time
```

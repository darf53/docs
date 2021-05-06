# How to use ldapsearch

```
ldapsearch -x -b "cn=Users,dc=dev,dc=acme,dc=test" -H ldap://10.0.1.18 -D "cn=Administrator,cn=Users,dc=dev,dc=acme,dc=test" -w xxxxxx "sAMAccountName=*" userPrincipalName 
```

Or to delete a user
```
ldapdelete -v -c -D "cn=Administrator,cn=Users,dc=dev,dc=acme,dc=test" -W  sAMAccountName=user_to_delete
```
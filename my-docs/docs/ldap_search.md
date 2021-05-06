# How to use ldapsearch

```
ldapsearch -x -b "cn=Users,dc=dev,dc=acme,dc=test" -H ldap://10.0.1.18 -D "cn=Administrator,cn=Users,dc=dev,dc=acme,dc=test" -w xxxxxx "sAMAccountName=*" userPrincipalName 
```

Or to delete a user
```
ldapdelete -v -c -D "cn=Administrator,cn=Users,dc=dev,dc=acme,dc=test" -W  sAMAccountName=user_to_delete
```

Adding a user
```
ldapadd -h  localhost  -D cn=Administrator -w password -f user3.ldif
```
Below are contents of user3.ldif
```
dn: cn=user3,cn=Users,dc=acme,dc=com
changetype: add
uid: user3
mail: user
givenName: user3
cn: testuser
sn: testuser
userpassword: abc
description:  user3 description
objectClass: top
objectClass: person
objectClass: organizationalperson
objectClass: inetorgperson
objectClass: orcluser
objectClass: orcluserV2
```
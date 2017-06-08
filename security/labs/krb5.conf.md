# krb5.conf

Command:
```
vi /etc/krb5.conf
```

Result:
```
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = SEBC
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true

[realms]
 SEBC = {
  kdc = node01.sebc
  admin_server = node01.sebc
 }

[domain_realm]
 .sebc = SEBC
 sebc = SEBC
 ```
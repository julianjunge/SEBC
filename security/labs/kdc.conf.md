[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 example.com = {
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal
max_life = 1d
max_renewable_life = 7d 0h 0m 0s
default_principal_flags = +renewable
 }


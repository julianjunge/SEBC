includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 dns_lookup_realm = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = aes256-cts
 default_tkt_enctypes = aes256-cts
 rdns = false
#pkinit_anchors = /etc/pki/tls/certs/ca-bundle.crt
 default_realm = EXAMPLE.COM
#default_ccache_name = KEYRING:persistent:%{uid}

[realms]
 EXAMPLE.COM = {
 kdc = ip-10-0-0-136.ec2.internal
 admin_server = ip-10-0-0-136.ec2.internal
 }

[domain_realm]
   .ip-10-0-0-136.ec2.internal = EXAMPLE.COM
   ip-10-0-0-136.ec2.internal = EXAMPLE.COM

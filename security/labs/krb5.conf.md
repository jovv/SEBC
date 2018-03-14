# Configuration snippets may be placed in this directory as well
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
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac
 rdns = false
 default_realm = JOVV.HADOOP.COM
 default_ccache_name = KEYRING:persistent:%{uid}

[realms]
 JOVV.HADOOP.COM = {
  kdc = ip-172-31-2-135.eu-west-1.compute.internal
  admin_server = ip-172-31-2-135.eu-west-1.compute.internal
 }

[domain_realm]
 .eu-west-1.compute.internal = JOVV.HADOOP.COM
 eu-west-1.compute.internal = JOVV.HADOOP.COM

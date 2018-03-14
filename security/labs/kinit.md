# Integrating Kerberos with Cloudera Manager

```
    kinit cloudera-scm
```

Output

```    
    [8446] 1521037740.307591: Getting initial credentials for cloudera-scm@JOVV.HADOOP.COM
    [8446] 1521037740.307820: Sending request (184 bytes) to JOVV.HADOOP.COM
    [8446] 1521037740.307871: Resolving hostname ip-172-31-2-135.eu-west-1.compute.internal
    [8446] 1521037740.308585: Initiating TCP connection to stream 172.31.2.135:88
    [8446] 1521037740.308671: Sending TCP request to stream 172.31.2.135:88
    [8446] 1521037740.309160: Received answer (854 bytes) from stream 172.31.2.135:88
    [8446] 1521037740.309178: Terminating TCP connection to stream 172.31.2.135:88
    [8446] 1521037740.461215: Response was not from master KDC
    [8446] 1521037740.461281: Processing preauth types: 19, 3, 11
    [8446] 1521037740.461308: Selected etype info: etype rc4-hmac, salt "JOVV.HADOOP.COMcloudera-scm", params ""
    [8446] 1521037740.461342: Produced preauth for next request: (empty)
    [8446] 1521037740.461352: Getting AS key, salt "JOVV.HADOOP.COMcloudera-scm", params ""
    Password for cloudera-scm@JOVV.HADOOP.COM:
    [8446] 1521037744.155794: AS key obtained from gak_fct: rc4-hmac/7EB8
    [8446] 1521037744.155886: Decrypted AS reply; session key is: rc4-hmac/EAEE
    [8446] 1521037744.155906: FAST negotiation: available
    [8446] 1521037744.155934: Initializing KEYRING:persistent:0:0 with default princ cloudera-scm@JOVV.HADOOP.COM
    [8446] 1521037744.155981: Storing cloudera-scm@JOVV.HADOOP.COM -> krbtgt/JOVV.HADOOP.COM@JOVV.HADOOP.COM in KEYRING:persistent:0:0
    [8446] 1521037744.156031: Storing config in KEYRING:persistent:0:0 for krbtgt/JOVV.HADOOP.COM@JOVV.HADOOP.COM: fast_avail: yes
    [8446] 1521037744.156049: Storing cloudera-scm@JOVV.HADOOP.COM -> krb5_ccache_conf_data/fast_avail/krbtgt\/JOVV.HADOOP.COM\@JOVV.HADOOP.COM@X-CACHECONF: in KEYRING:persistent:0:0
```

```
    klist -e -f
```

```
    Ticket cache: KEYRING:persistent:0:0
    Default principal: cloudera-scm@JOVV.HADOOP.COM

    Valid starting       Expires              Service principal
    03/14/2018 14:29:00  03/15/2018 14:29:00  krbtgt/JOVV.HADOOP.COM@JOVV.HADOOP.COM
            renew until 03/21/2018 14:29:00, Flags: FRI
            Etype (skey, tkt): arcfour-hmac, aes256-cts-hmac-sha1-96
```
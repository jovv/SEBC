# Cloudera Manager Upgrade

## API commands

### API Version

```
    curl -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/version'
```

Output

```
    v19
```

### CM Version

```
    curl -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v19/cm/version'
```

Output

```
    {
    "version" : "5.14.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20180207-1728",
    "gitHash" : "f253d8e2b9cf5cb61a2f1ba1bf71de6fb603add0",
    "snapshot" : false
    }
```

### List all CM users

```
    curl -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v19/users'
```

```
    {
    "items" : [ {
        "name" : "admin",
        "roles" : [ "ROLE_LIMITED" ]
    }, {
        "name" : "jovv",
        "roles" : [ "ROLE_ADMIN" ]
    }, {
        "name" : "minotaur",
        "roles" : [ "ROLE_CONFIGURATOR" ]
    } ]
    }
```

### Report the database server type in use by CM (mysql, oracle, ...)

```
    curl -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v19/cm/scmDbInfo'
```

```
    {
    "scmDbType" : "MYSQL",
    "embeddedDbUsed" : false
    }
```
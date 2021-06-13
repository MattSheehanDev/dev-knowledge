Azure Redis Cache
============================

Verify a connection to an Azure Redis Cache
```
IDatabase database = ConnectionMultiplexer.Connect(connectionString).GetDatabase();
var result = database.Execute("PING").ToString();
```


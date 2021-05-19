Azure CLI
=================

Login to Azure account
```
az login
```

Show which account you are logged into
```
az account show
```

Show all subscriptions for your account
```
az account list --output table
```

Show all geographic locations available to your account
```
az account list-locations --output table
```

List resources in a Resource Group
```
az resource list -g <resource-group>
```


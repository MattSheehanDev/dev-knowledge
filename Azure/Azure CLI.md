Azure CLI
=================

Commands
---------------------

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

Recipes
------------------------
SSH into an Azure virtual machine
```
adminUser=`az vm show -g group1 -n vm1 --query osProfile.adminUsername`
publicIp=`az vm show -g group1 -n vm1 -d --query publicIps -o tsv`

ssh $adminUser@$publicIp
```

Enable Azure subscription to send events to Event Grid
```
az provider register --namespace Microsoft.EventGrid
```

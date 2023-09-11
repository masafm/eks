# ARO
1. Create resource group
2. Create subnet master-subnet and worker-subnet
3. Run az command
```
az aro create --resource-group masafumi-kashiwagi \
--name masafumi-kashiwagi \
--vnet masafumi-kashiwagi \
--master-subnet aro-master-subnet \
--worker-subnet aro-worker-subnet \
--pull-secret @pull-secret.txt
```

## Reference
* [How to use operators](https://learn.microsoft.com/en-us/azure/openshift/tutorial-create-cluster#get-a-red-hat-pull-secret-optional)
* [How to install Datadog Agent](https://github.com/DataDog/datadog-operator/blob/main/docs/install-openshift.md)


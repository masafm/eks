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
--worker-count 3 \
--pull-secret @pull-secret.txt
```

## When ARO is behind Azure firewall
1. Dnat 80,443,6443
2. Add route for Firewall PIP to Internet
3. Change hosts file
```
FirewallPip console-openshift-console.apps.xxx.japaneast.aroapp.io
FirewallPip	oauth-openshift.apps.xxx.japaneast.aroapp.io
FirewallPip api.xxx.japaneast.aroapp.io
```

## Reference
* [How to use operators](https://learn.microsoft.com/en-us/azure/openshift/tutorial-create-cluster#get-a-red-hat-pull-secret-optional)
* [How to access Azure public LB behind Azure firewwall](https://learn.microsoft.com/ja-jp/azure/firewall/integrate-lb)
* [How to install Datadog Agent](https://github.com/DataDog/datadog-operator/blob/main/docs/install-openshift.md)

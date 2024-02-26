# EKS Fargate

```
eksctl create cluster --name masafumi-kashiwagi-eks-fargate-osaka --fargate --region ap-northeast-3
kubectl create secret generic datadog-secret --from-literal api-key=$DD_API_KEY --from-literal app-key=$DD_APP_KEY
kubectl apply -f rbac.yaml
helm install datadog-cluster-agent -f datadog-cluster-agent.yaml --set targetSystem=linux datadog/datadog
kubectl apply -f datadog-agent.yaml
```

# eks
commands

```
eksctl create cluster -f cluster-tokyo.yaml
# For persistent volume
eksctl utils associate-iam-oidc-provider --region=ap-northeast-1 --cluster=MasafumiKashiwagiEks --approve
eksctl create iamserviceaccount --name ebs-csi-controller-sa --namespace kube-system --cluster MasafumiKashiwagiEks --attach-policy-arn arn:aws:iam::aws:policy/service-role/AmazonEBSCSIDriverPolicy --approve --role-only --role-name MasafumiKashiwagiEksEbsCsiDriverRole --region ap-northeast-1
eksctl create addon --name aws-ebs-csi-driver --cluster MasafumiKashiwagiEks --service-account-role-arn arn:aws:iam::$(aws sts get-caller-identity --query Account --output text):role/MasafumiKashiwagiEksEbsCsiDriverRole --region ap-northeast-1 --force
```
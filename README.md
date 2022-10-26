# sample-infra

## Create infraestructure

We will need to set the AWS credentials locally first. After they are set we can run:

``` sh
cd envrionments/env/dev
terraform apply
```

## Destroy infraestructure

Destroy workloads projects created on Argocd. This is required to avoid dependencies conflicts on aws-load-balancer-controller and the workloads ingress.

``` sh
cd envrionments/env/dev
terraform destroy -target=module.eks_blueprints_kubernetes_addons -auto-approve
terraform destroy -target=module.eks_blueprints -auto-approve
terraform destroy -auto-approve
```

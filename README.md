I'm using this setup as my playground

## Versions
```
$ aws --version
aws-cli/2.8.7 Python/3.9.11 Linux/5.19.16-76051916-generic exe/x86_64.ubuntu.22 prompt/off
```

```
$ kubectl version --short
Client Version: v1.25.3
Kustomize Version: v4.5.7
```

```
$ helm version
version.BuildInfo{Version:"v3.10.1", GitCommit:"9f88ccb6aee40b9a0535fcc7efea6055e1ef72c9", GitTreeState:"clean", GoVersion:"go1.18.7"}
```
## Configure AWS CLI
```
$ aws configure
> AWS Access Key ID
> AWS Secret Access Key
```

## Deploy the EKS Cluster
```
terraform-eks/ 

$ terraform init
$ terraform plan
$ terraform deploy -auto-approve

## Configure kubectl to interact with the cluster ##
$ aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)
```

## Destroy your Cluster
```
terraform-eks/ 

$ terraform destroy -auto-approve
```
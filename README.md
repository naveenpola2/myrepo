# CI/CD on AWS with Terraform, EKS, ArgoCD

## 🔧 Provisioning Cluster

```bash
cd terraform
terraform init
terraform apply
aws eks --region <region> update-kubeconfig --name devops-eks

 Deploying NGINX with ArgoCD

kubectl apply -f argocd/nginx-app.yaml

ArgoCD Access

kubectl get svc -n argocd
# Visit external IP from browser

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

 NGINX Access

kubectl get svc nginx-service
# Use LoadBalancer IP or port-forward


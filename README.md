"# Devops-2025-project" 
"# Devops-2025-project" 
"# Devops-2025-project" 
CI/CD pipeline using Docker, Kubernetes, Istio, Terraform, Ansible, Trivy,Jenkins, grafanna, load balancer, kalie
Pipeline Workflow

1. Build: Docker image creation using `Dockerfile`.
2. Test: Run unit tests for validation.
3. Scan: Vulnerability scanning with Trivy.
4. Deploy: Use Jenkins to deploy the application on Kubernetes.
5. Provision Infrastructure: Automate infrastructure creation using Terraform.
6. Configure Servers: Use Ansible to configure application servers.
7. Service Mesh: Secure microservices communication using Istio.
 STEPS  
Aws Configure
https://github.com/eksctl-io/eksctl/releases

eksctl create cluster --name devopsproject
https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
kubectl port-forward svc productpage 80:9080
 for deleting pods
kubectl delete all --all
kubectl create namespace argocd kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl config set-context --current --namespace=argocd

https://github.com/argoproj/argo-cd/releases

argocd login --core or cd Downloads ./argocd-windows-amd64.exe login --core

argocd admin initial-password -n argocd or ./argocd-windows-amd64.exe admin initial-password -n argocd

kubectl port-forward svc/argocd-server -n argocd 8080:443
git add . git commit -m first . git push

kubectl get pods -n default

kubectl port-forward svc/productpage -n default 80:9080

http://127.0.0.1/productpage

https://github.com/istio/istio/releases/tag/1.24.2

istioctl install --set profile=demo

kubectl get pods -n istio-system

kubectl get svc -n istio-system

kubectl label namespace default istio-injection=enabled

kubectl delete pods --all -n default

kubectl get pods -n default

kubectl apply -f bookinfo-gateway.yaml

### Create Helm chart skeleton
```
helm create eks
cd eks
```

### Add resource files in templates
### Lint the chart
```
helm lint .
````
### Package the chart
```
helm package .
```
### Generate Helm repo index
```
helm repo index . --url https://LikhithaGopireddy.github.io/terraform-kubernetes-helm
```
### Clone your GitHub repo
```
git clone https://github.com/LikhithaGopireddy/terraform-kubernetes-helm.git
cd terraform-kubernetes-helm

```
### Copy chart files to repo
```
cp ../eks-0.1.0.tgz .
cp ../index.yaml .
```
### Commit and push to GitHub
```
git add eks-0.1.0.tgz index.yaml
git commit -m "Add eks Helm chart"
git push origin main
```
### Enable GitHub Pages

### Go to Settings → Pages in your GitHub repo.

### Source: Branch main, folder / (root)

### Save → GitHub will give URL:

### Verify GitHub Pages URL
# Open in browser
```
https://LikhithaGopireddy.github.io/terraform-kubernetes-helm/index.yaml
```
### Add Helm repo locally
```
helm repo add myrepo https://LikhithaGopireddy.github.io/terraform-kubernetes-helm
helm repo update
helm search repo eks
```
### Install chart on EKS
```
aws eks --region us-east-1 update-kubeconfig --name prod-eks-cluster
```
```
kubectl get nodes
kubectl get pods --all-namespaces
```
```
helm install eks myrepo/eks
```


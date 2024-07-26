```markdown
# Setting up a Kubernetes Cluster with ArgoCD using kind

## Step 1: Create a Cluster with kind

Create a Kubernetes cluster named `argocd` using the following command:

```sh
kind create cluster --name argocd
```

## Step 2: Switch to the Cluster Context

Switch to the newly created cluster context:

```sh
kubectl cluster-info --context kind-argocd
```

## Step 3: Create ArgoCD Namespace

Create the `argocd` namespace with the following commands:

```sh
kubectl create ns argocd --dry-run=client -o yaml > namespace.yml
kubectl apply -f namespace.yml
```

## Step 4: Install ArgoCD by Official Manifest

Install ArgoCD in the `argocd` namespace using the official manifest:

```sh
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Step 5: Create Access to ArgoCD from Your Local Machine

Set up port forwarding to access ArgoCD from your local machine on port 8080:

```sh
kubectl port-forward svc/argocd-server -n argocd 8080:443 &
```

> Note: This uses a self-signed SSL certificate. You can ignore the warning for now. More elegant ways to get GUI access will be covered in future articles.

## Step 6: Get ArgoCD Admin Password

Retrieve and decrypt the ArgoCD admin password:

```sh
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
```

# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

**
#**Private Repo means**
-------------------------**Git Hub Setting** ---------------------------
Create token  Github  Settings  Developer Settings  Token Classic  Generate new token Classic  Select permissions Generate

----Argo Setting--------------------
Settings  Repositories  Connect Repo  Via HTTPS  git  project – Default  Repository URL - https://github.com/Anand-1992/Argo-cd.git  Username ( Anand-1992)  Password (ghp_mThwNKgsVeAijq22cIasJopu7HQ9tuI4X67C0) Connect Status(Success)
----------------------------------------------------------------------

```sh
cd argocd-install/
pwd
```

```sh {"cwd":"/Users/aina/Desktop/argocd/argocd-install"}
helm install argocd ./argo-cd \
    --namespace=argocd \
    --create-namespace \
    -f values-override.yaml
```

```sh
kubectl -n argocd get pods
```

Password 

```sh
kubectl -n argocd get secrets argocd-initial-admin-secret \
    -o jsonpath='{.data.password}' | base64 -d
```

foward

```sh
kubectl -n argocd port-forward service/argocd-server 8080:80
```

```sh
Open http://localhost:8080
```
# Flux CD bootstrap

```bash
# Install flux
kubectl apply -f k8s/flux/_namespace.yaml
helm install flux -f k8s/flux/flux-values.yaml -n flux fluxcd/flux

# After it's running, grab the SSH pubkey and add to the repo
fluxctl identity

# Install Helm operator
helm install helm-operator -f k8s/flux/helm-operator-values.yaml -n flux fluxcd/helm-operator
```

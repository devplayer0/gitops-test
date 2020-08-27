# Flux CD bootstrap

```bash
# Install flux
kubectl apply -f k8s/flux/_namespace.yaml
yq r k8s/flux/flux.yaml spec.values | helm install flux -f - -n flux fluxcd/flux

# After it's running, grab the SSH pubkey and add to the repo
fluxctl identity

# Install Helm operator
yq r k8s/flux/helm-operator.yaml spec.values | helm install helm-operator -f - -n flux fluxcd/helm-operator
```

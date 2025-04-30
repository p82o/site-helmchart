helm upgrade --install ingress-nginx ingress-nginx \
  --namespace ingress-nginx \
  --create-namespace \
  --repo https://kubernetes.github.io/ingress-nginx \
  --values ./ingress-controller/values.yaml

helm repo add jetstack https://charts.jetstack.io --force-update
helm upgrade --install cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --create-namespace \
  --version v1.17.2 \
  --values ./cert-manager/values.yaml

helm install site-chart ./site-chart

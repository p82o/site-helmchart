helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --values ./ingress-controller/values.yaml \
  --namespace ingress-nginx --create-namespace

helm install site-chart ./site-chart

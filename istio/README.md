kubectl config set-context $(kubectl config current-context) --namespace=istio-bsm
# istioctl kube-inject
kubectl label namespace istio-bsm istio-injection=enabled
istioctl proxy-config routes deploy/istio-ingressgateway.istio-system


## ArgoCD
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

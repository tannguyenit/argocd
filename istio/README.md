kubectl config set-context $(kubectl config current-context) --namespace=istio-bsm
# istioctl kube-inject
kubectl label namespace istio-bsm istio-injection=enabled
istioctl proxy-config routes deploy/istio-ingressgateway.istio-system
## Getting started
![URL](https://istio.io/latest/docs/setup/getting-started/)
#### Follow these steps to get started with Istio:
1.  [Download and install Istio](https://istio.io/latest/docs/setup/getting-started/#download)
2.  [Deploy the sample application](https://istio.io/latest/docs/setup/getting-started/#bookinfo)
3.  [Open the application to outside traffic](https://istio.io/latest/docs/setup/getting-started/#ip)
4.  [View the dashboard](https://istio.io/latest/docs/setup/getting-started/#dashboard)

## Download Istio
1. Get lastest Istio release: <code>curl -L https://istio.io/downloadIstio | sh - </code>
2. cd istio-1.15.0
3. export PATH=$PWD/bin:$PATH
## Install Istio

1. istioctl install --set profile=demo -y
2. kubectl label namespace default istio-injection=enabled
## Deploy the sample application
1. kubectl apply -f [samples/bookinfo/platform/kube/bookinfo.yaml](https://raw.githubusercontent.com/istio/istio/release-1.15/samples/bookinfo/platform/kube/bookinfo.yaml)
2. kubectl get services
3. kubectl get pods
4. kubectl exec "$(kubectl get pod -l app=ratings -o jsonpath='{.items[0].metadata.name}')" -c ratings -- curl -sS productpage:9080/productpage | grep -o "<title>.*</title>"

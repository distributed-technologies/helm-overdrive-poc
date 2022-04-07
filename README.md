To deploy on cluster, you need to have the helm-overdrive CLI tool on your pc for now.


and have a kubeconfig to your cluster
then from the root of this repo run
``` bash
namespace=argocd
kubectl create ns $namespace

./helm-overdrive template \
-c helm-overdrive.yaml \
--application_folder services/argocd \
--app_name argocd \
--chart_name argo-cd \
--chart_version "4.4.0" \
--helm_repo https://argoproj.github.io/argo-helm | kubectl apply -n $namespace -f -
```

## Clone the repository 
```
git clone https://github.com/ckadarla/k8s.git
```
## Change to the folder
```
cd k8s/Skooner-Dashboard
```
## Apply mainfest files for Skooner from folders 
```
kubectl apply -f .
```
## Do port forwarding to the Skooner Dashboard
```
kubectl port-forward deployment/skooner --address 0.0.0.0 8080:4654 -n kube-system
``` 
## Give that service account root on the cluster
```
kubectl create clusterrolebinding skooner-sa --clusterrole=cluster-admin --serviceaccount=kube-system:skooner-sa
```
## Create the service account in the current namespace (we assume default)
```
kubectl create serviceaccount skooner-sa -n kube-system
```
## For Kubernetes v1.21 or lower
## Find the secret that was created to hold the token for the SA
```
kubectl get secrets
```
## Show the contents of the secret to extract the token
```
kubectl describe secret skooner-sa-token-xxxxx
```
## For Kubernetes v1.22 or higher
```
kubectl create token skooner-sa
```

Ref:  https://raw.githubusercontent.com/skooner-k8s/skooner/master/kubernetes-skooner.yaml

https://github.com/skooner-k8s/skooner#kubectl-proxy
 

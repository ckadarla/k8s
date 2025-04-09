## Clone the repository 
```
git clone https://github.com/ckadarla/k8s.git
```
## Change to the folder
```
cd k8s/nginx sample
```
## Apply mainfest files for Skooner from folders 
```
kubectl apply -f .
```
## do port forward so that you can access from local for Voting App
```
kubectl port-forward svc/nginx 8080:80 
```

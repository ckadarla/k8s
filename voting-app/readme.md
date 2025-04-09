## Clone the repository 
```
git clone https://github.com/ckadarla/k8s.git
```
## Change to the folder
```
cd k8s/voting-app
```
## Apply mainfest files for Skooner from folders 
```
kubectl apply -f .
```
## do port forward so that you can access from local for Voting App
```
kubectl port-forward svc/vote 8080:8080 -n jupyter
```
## do port forward so that you can access from local for Voting Result
```
kubectl port-forward svc/result 8081:8081 -n jupyter
```
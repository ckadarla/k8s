## Clone the repository 
git clone https://github.com/ckadarla/k8s.git

## Change to the folder
cd k8s/Jupyter-app

## Apply mainfest files for Skooner from folders 
kubectl apply -f .

# do port forward so that you can access from local 
kubectl port-forward svc/jupyter-svc 8888:8888 -n jupyter
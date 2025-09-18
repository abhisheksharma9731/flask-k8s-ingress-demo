cat > README.md <<'EOF'
# flask-k8s-ingress-demo

Simple Flask app + Kubernetes Ingress demo.

## Run locally (docker)
docker build -t abhisheksharma9731/flask-k8s-ingress-demo:latest .
docker run -p 5000:5000 abhisheksharma9731/flask-k8s-ingress-demo:latest

## Kubernetes (Minikube)
minikube start
minikube addons enable ingress
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml

#To access:
MINIKUBE_IP=\$(minikube ip)
#add to /etc/hosts: "<MINIKUBE_IP> flask-ingress.local"
#then open: http://flask-ingress.local
EOF

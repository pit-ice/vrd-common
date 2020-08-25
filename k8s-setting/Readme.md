# Azure Kubernetes 설정

## Ubuntu setting

1. curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -
2. sudo apt-get install apt-transport-https --yes
3. echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
4. sudo apt-get update
5. sudo apt-get install helm


## ingress controller 설정

1. kubectl create namespace ingress-basic
2. helm repo add stable https://kubernetes-charts.storage.googleapis.com/
3.helm install nginx-ingress stable/nginx-ingress \
    --namespace ingress-basic \
    --set controller.replicaCount=2 \
    --set controller.nodeSelector."beta\.kubernetes\.io/os"=linux \
    --set defaultBackend.nodeSelector."beta\.kubernetes\.io/os"=linux
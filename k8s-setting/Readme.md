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


## ingress tls 설정

### 1. secret 생성
- 인증서가 있는 경로에서 아래 명령어로 생성한다.
- 명령어
    ```sh
    kubectl create secret tls vrd-tls-secret \
    --cert wild.skccvrd.kubepia.net.crt \
    --key wild.skccvrd.kubepia.net.key \
    -n vrd-dev
    ```
### 2. ingress yaml에 tls 설정 추가

- metadata.annotations 에 nginx.ingress.kubernetes.io/ssl-redirect: "true" 추가
- spec.tls 추가

    ```yaml
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress
    metadata:
    name: vrd-public-api
    namespace: vrd-dev
    annotations:
        kubernetes.io/ingress.class: nginx
        nginx.ingress.kubernetes.io/ssl-redirect: "true"
        
        ...

    spec:
    tls:
        - hosts:
            - api.skccvrd.kubepia.net
        secretName: vrd-tls-secret
    rules:
    - host: api.skccvrd.kubepia.net
        http:
        paths:
        
        ...

    ```
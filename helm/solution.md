# Helm

## Partie 1

```sh
brew install helm

helm repo add stable https://charts.helm.sh/stable

helm repo list

helm create my-nginx

helm install my-nginx my-nginx

helm list

minikube service my-nginx
```
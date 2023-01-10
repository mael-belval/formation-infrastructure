# Solution

## Feedback

- Ajouter des ressources à lire ?
- Préciser l'attendu ? (Ligne de commandes, conf, ...)

## Partie 1

```sh
minikube start

#kubectl run nginx --image=nginx

#kubectl get pods

#kubectl delete pod nginx

kubectl create deployment nginx --image=nginx --replicas=2

kubectl get deployments

kubectl get pods

kubectl create service clusterip nginx --tcp=80:80

minikube service nginx
```

## Partie 2

```sh
minikube addons enable ingress

kubectl apply -f nginx-ingress.yaml

kubectl get ingress

echo "127.0.0.1 nginx.minikube" > /etc/hosts

minikube tunnel

curl nginx.minikube
```

## Partie 3

```sh
kubectl apply --validate=false -f https://github.com/cert-manager/cert-manager/releases/download/v1.10.1/cert-manager.yaml

kubectl delete service nginx

kubectl create service clusterip nginx --tcp=443:80

kubectl apply -f clusterIssuer.yaml

kubectl apply -f certificat.yaml

kubectl apply -f nginx-ingress.yaml
```

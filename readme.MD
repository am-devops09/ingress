## website where i find the right config

https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/

minikube addons enable ingress

kubectl get pods -n ingress-nginx

kubectl create deployment web --image=gcr.io/google-samples/hello-app:1.0

kubectl expose deployment web --type=NodePort --port=8080

kubectl get service web

minikube service web --url

example-ingress.yaml

kubectl apply -f example-ingress.yaml

kubectl get ingress

curl --resolve "hello-world.info:80:$( minikube ip )" -i http://hello-world.info

minikube ip

kubectl create deployment web2 --image=gcr.io/google-samples/hello-app:2.0

kubectl expose deployment web2 --port=8080 --type=NodePort

add config to yaml file 

kubectl apply -f example-ingress.yaml

curl --resolve "hello-world.info:80:$( minikube ip )" -i http://hello-world.info

curl --resolve "hello-world.info:80:$( minikube ip )" -i http://hello-world.info/v2
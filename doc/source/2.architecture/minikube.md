# Minikube


## Install

* Intall minikube on ubuntu 22.04 in AMD64 architecture

```
curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64

minikube start

curl -LO https://dl.k8s.io/release/v1.32.0/bin/linux/amd64/kubectl
kubectl get po -A
```

## Test

```
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
kubectl expose deployment hello-minikube --type=NodePort --port=8080
#kubectl port-forward service/hello-minikube 7080:8080
kubectl port-forward --address 0.0.0.0 service/hello-minikube 7080:8080

kubectl get services hello-minikube
```

then you can open http://192.168..0.1:7080/ by your browser

## dashboard

```shell
minikube addons enable dashboard
kubectl port-forward --address 0.0.0.0 service/kubernetes-dashboard -n kubernetes-dashboard 8080:80
```
then you can open http://192.168.0.1:8080/ by your browser

## Reference
* https://minikube.sigs.k8s.io/docs/handbook/
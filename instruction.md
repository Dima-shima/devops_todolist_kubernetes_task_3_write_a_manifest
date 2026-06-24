kubectl apply -f .infrastructure/namespace.yml

kubectl apply -f .infrastructure/busybox.yml

kubectl apply -f .infrastructure/todoapp-pod.yml

kubectl port-forward pod/todoapp 8081:8080 -n todoapp
brauser: localhost:8081

kubectl get pods -o wide -n todoapp
kubectl exec -it -n todoapp busybox -- sh
root@busybox:/]$ curl 10.244.0.6:8080
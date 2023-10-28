# Comandos utilizados 
* kubectl get pods -n kube-system
* kubectl get pods -n kube-system -o wide

kubectl get pods -A

kubectl get service

kubectl get replicaset -A

kubectl get po

kubectl get svc

kubectl get ns

kubectl run --image nginx --port 80 rai --dry-run=client -o yaml > pod.yaml

kubectl get pods -o wide

kubectl get pods -L run  ->mostra os pods com a label "run"

kubectl run -ti ironman --image ubuntu

kubectl exec -it ironman -- bash

kubectl attach ironman -c ironman -ti

kubectl cp rai.txt  ironman:/home/rai.txt

kubectl exec ironman -- cat /home/rai.txt

kubectl get pods -w

kubectl delete -f pod.yaml

# Comandos utilizados 

# Instala o Docker 
* sudo curl -fsSL https://get.docker.com | bash
* sudo usermod -aG docker rnrneves
* sudo chmod 666 /var/run/docker.sock

# Instala o kubectl no Linux 
* curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
* chmod +x ./kubectl
* sudo mv ./kubectl /usr/local/bin/kubectl
* kubectl version --client
  
# Instala o Kind no Linux 
* curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64
* chmod +x ./kind
* sudo mv ./kind /usr/local/bin/kind

# Comandos utilizados para pod
* kubectl get pods -n kube-system
* kubectl get pods -n kube-system -o wide
* kubectl get pods -A
* kubectl get service
* kubectl get replicaset -A
* kubectl get po
* kubectl get svc
* kubectl get ns
* kubectl run --image nginx --port 80 rai --dry-run=client -o yaml > pod.yaml
* kubectl get pods -o wide
* kubectl get pods -L run  ->mostra os pods com a label "run"
* kubectl run -ti ironman --image ubuntu
* kubectl exec -it ironman -- bash
* kubectl attach ironman -c ironman -ti
* kubectl cp rai.txt  ironman:/home/rai.txt
* kubectl exec ironman -- cat /home/rai.txt
* kubectl get pods -w
* kubectl delete -f pod.yaml

# Comandos utilizados para Deployment
* kubectl get deployments.apps
* kubectl get deployment
* kubectl get deploy
* kubectl get deploy -o yaml
* kubectl get pods -l app=nginx-deployment
* kubectl get replicaset
* kubectl describe deployment nginx-deployment
* kubectl delete -f deployment.yaml
* kubectl create deployment --image nginx --replicas 3 nginx-deployment
* kubectl create deployment --image nginx --replicas 3 nginx-deployment --dry-run=client
* kubectl create deployment --image nginx --replicas 3 nginx-deployment --dry-run=client -o yaml
* kubectl create deployment --image nginx --replicas 3 nginx-deployment --dry-run=client -o yaml > new-deployment.yaml
* kubectl exec -ti nginx-deployment-66fb7f764c-8k4xx -- bash
* cat /proc/1/cmdline  ->Comando executado dentro do container
* kubectl create namespace rai-teste
* kubectl get namespaces 
* kubectl create namespace rai-teste --dry-run=client -o yaml
* kubectl get deploy -n rai-teste
* kubectl get pods -n rai-teste
* kubectl exec -it -n rai-teste nginx-deployment-7d89c5876d-58r6f -- nginx -v
* kubectl  describe deploy -n rai-teste nginx-deployment
* kubectl rollout status deployment -n rai-teste nginx-deployment
* kubectl rollout undo deploy -n rai-teste nginx-deployment
* kubectl rollout history deploy -n rai-teste nginx-deployment
* kubectl rollout history deploy -n rai-teste nginx-deployment --revision 3
* kubectl rollout undo deployment -n rai-teste nginx-deployment --to-revision=3
* kubectl rollout pause deploy  -n rai-teste nginx-deployment
* kubectl rollout resume deploy  -n rai-teste nginx-deployment
* kubectl rollout restart deploy  -n rai-teste nginx-deployment

# Comandos utilizados no Day 4
* kubectl apply -f deploy-replicaset.yaml
* kubectl get pods
* kubectl get replicaset
* kubectl get rs
* kubectl rollout undo deployment nginx-deployment
* kubectl scale deployment nginx-deployment --replicas 3
* kubectl delete pod nginx-tio-rai-t5pgs
* kubectl delete pod nginx-tio-rai-dmdr5 nginx-tio-rai-sq5qs
* kubectl get pods -o=jsonpath='{range .items[*]}{"\n"}{.metadata.name}{"\t"}{range .spec.containers[*]}{.image}{"\t"}{end}{end}'
* kubectl get daemonset
* kubectl get ds
* kubectl get pods -o wide -l app=node-exporter-daemonset
* kubectl exec --stdin --tty nginx-deployment-588695ddf8-jbqvl -- /bin/bash   --> Acessa um pod
* watch kubectl get pods 

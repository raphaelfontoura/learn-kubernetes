## No Linux:

> Instale o kubectl e o minikube.

Rode o minikube.
```bash
minikube start
```
É possível selecionar o driver com o comando:
```bash
minikube start --vm-driver=virtualbox
```

Rode o comando para verificar informações do cluster
```bash
kubectl cluster-info
```
Comando para verificar os nodes:
```bash
kubectl get nodes
```

Para criar um pod o comando será como exemplo abaixo:
```bash
kubectl run nginx-pod --image=nginx:latest
```
Para monitorar um pod
```bash
kubectl get pods --watch
```
Outro comando para verificar informações de rede de um pod:
```bash
kubectl get pods -o wide
```

para descrever um pod:
```bash
kubectl describe pod nginx-pod
```

Para mudar a versão do pod:
```bash
kubectl edit pod nginx-pod
```

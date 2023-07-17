Chegou a hora de você seguir todos os passos realizados por mim durante esta aula, preparando o seu ambiente de homologação:

- Criar uma instância EC2

- Instalar o ***Kubernetes command-line tool*** (**kubectl**):
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.13.0/bin/linux/amd64/kubectl
```

- Dar permissão de execução para o `kubectl`:
```bash
chmod +x kubectl
```

- Movê-lo o `kubectl` para a pasta dos binários:
```bash
sudo mv kubectl /usr/local/bin/
```

- Instalar o **Docker**:
```bash
sudo apt-get install docker.io
```

- Instalar o **Minikube**:
```bash
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
  && chmod +x minikube
```

- Inicializar o **Minikube**:
```bash
minikube start --vm-driver=none
```
- Configurar as permissões do **Minikube**

- Modificar o arquivo **~/.kube/config** para ter o *path* do usuário em vez do **root**

- Realizar o teste do ambiente com o **hello-minikube** de exemplo:
```bash
kubectl create run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 -- port=8080
```

- Expor a porta do **hello-minikube**:
```bash
kubectl expose deployment hello-minikube --type=NodePort
```

- Criar um *security group* para o **minikube** e associá-lo à sua instância

Caso já tenha feito, excelente. Se ainda não, é importante que você execute o que foi visto nos vídeos para poder continuar com a próxima aula.
Chegou a hora de você seguir todos os passos realizados por mim durante esta aula:

- Fazer o download da aplicação **guestbook** [aqui](https://caelum-online-public.s3.amazonaws.com/1087-amazon-eks-kubernetes/02/arquivos.zip)

- Fazer o *deploy* e criar o serviço do Redis Master:

```bash
kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/redis-master-deployment.yaml

kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/redis-master-service.yaml
```

- Fazer o *deploy* e criar o serviço do Redis Slave:
```bash
kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/redis-slave-deployment.yaml

kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/redis-slave-service.yaml
```
- Fazer o *deploy* e criar o serviço do front-end da aplicação:
```bash
kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/frontend-deployment.yaml

kubectl apply -f https://raw.githubusercontent.com/ricardomerces/guestbook-app/master/frontend-service.yaml
```

- Testar a aplicação

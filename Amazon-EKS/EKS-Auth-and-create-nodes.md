Chegou a hora de você seguir todos os passos realizados por mim durante esta aula:

- Instalar e configurar o **aws-iam-authenticator**:
```bash
curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.11.5/2018-12-06/bin/linux/amd64/aws-iam-authenticator

chmod +x aws-iam-authenticator

mv aws-iam-authenticator ~/.local/bin

aws eks update-kubeconfig --name producao
```
- Criar os *nodes*, através do **AWS CloudFormation**

- Adicionar os *nodes* ao *cluster*
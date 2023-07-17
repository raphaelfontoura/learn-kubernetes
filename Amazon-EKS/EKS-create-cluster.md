Chegou a hora de você seguir todos os passos realizados por mim durante esta aula:

- Criar uma *role* no AWS IAM, para o serviço **EKS**

- Criar uma VPC separada para o **EKS**, através do **AWS CloudFormation**

- Criar o *cluster*:
```bash
aws eks create-cluster --name producao --role-arn ARN_DA_ROLE_AQUI --resources-vpc-config subnetIds=SUBNET_ID_1_AQUI,SUBNET_ID_2_AQUI,SUBNET_ID_3_AQUI,securityGroupIds=SECURITY_GROUP_DA_VPC_AQUI
```
- Visualizar o cluster pela AWS CLI e pelo console
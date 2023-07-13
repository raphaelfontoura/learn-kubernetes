Nesta aula nós publicamos a aplicação AluraSports no AKS. Para nos conectar ao cluster do AKS executamos alguns comandos com o `az`:

Para logar no az:

```bash
az login
```

Para obter as credenciais do AKS:

```bash
az aks get-credentials --resource-group alurasports-rg --name k8s
```

Após isto, executamos os mesmos comandos no `kubectl` da [aula anterior](link da atividade da aula anterior) para a criação dos serviços da aplicação.
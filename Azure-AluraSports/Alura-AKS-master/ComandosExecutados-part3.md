Criação do grupo de recursos:

```bash
az group create az-alurasports-rg
```
Criação do nosso cluster AKS:

```bash
az aks create --name az-k8s --resource-group az-alurasports-rg --node-count 1 --location eastus --kubernetes-version 1.10.8 --generate-ssh-keys
```
Mudar o número de nós em nosso cluster:

```bash
az aks scale --node-count 3 --name az-k8s --resource-group az-alurasports-rg
```
Obter as atualizações disponíveis ao cluster:

```bash
az aks get-upgrades --name az-k8s --resource-group az-alurasports-rg --output table
```
Aplica atualização no cluster:

```bash
az aks upgrade --name az-k8s --resource-group alurasports-rg --kubernetes-version 1.11.3
```
Criar registro de imagens de containers:

```bash
az acr create --name azregistryalura --resource-group az-alurasports-rg --sku Basic --location eastus
```
Para mais comandos do Az para gerenciamento dos recursos do Azure, dê uma olhada na página da [documentação](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest).
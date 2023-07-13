Estes são os comandos executados em aula. Note que estou utilizando o nome do registro de imagens `registryalura`. Quando for executar em sua máquina, lembre-se de trocar o nome do registro para o nome do seu registro em sua conta do Azure.

Para fazer o login em nosso registro, executamos:

```bash
az acr login --name registryalura
```
Realizamos o pull da imagem `rafanercessian/aplicacao-loja` com a tag `v1` do docker hub:

```bash
docker pull rafanercessian/aplicacao-loja:v1 
```
Em seguida, criamos a tag adicionando o nome do registro `registryalura.azurecr.io`:

```bash
docker tag rafanercessian/aplicacao-loja:v1 registryalura.azurecr.io/loja/aplicacao-loja:v1
```
Para fazer o upload ao nosso registro do Azure, usamos:

```bash
docker push registryalura.azurecr.io/loja/aplicacao-loja:v1
```
Agora, para utilizarmos esta imagem em nosso arquivo YAML devemos criar um `secret` contendo a senha de acesso ao registro. No portal do Azure, navegue até seu recurso de registro, vá em *Chaves de acesso* e copie a senha e o usuário para usar no comando:

```bash
kubectl create secret docker-registry <NOME_DO_SEGREDO> --docker-server <NOME_DO_REGISTRO>.azurecr.io --docker-username=<USUARIO> --docker-password <SENHA> --docker-email <SEU_EMAIL>
```
Na aula, usei o comando com os argumentos a seguir:

```bash
kubectl create secret docker-registry alura.registry.secret --docker-server registryalura.azurecr.io --docker-password GoatFGjDPccdIZUtmsqA7RTK6b=4Klq2 --docker-username=registryalura --docker-email alura.guicosta@outlook.com
```
Feito isso, no seu arquivo YAML, adicione em `spec`, no mesmo nível de `containers`, o campo `imagePullSecrets` com o nome do segredo:

```yaml
  imagePullSecrets:
    - name: alura.registry.secret
```

E altere o nome da imagem:

```yaml
spec:
  containers:
    - name: container-aplicacao-loja
      image: registryalura.azurecr.io/alurasports/aplicacao-loja:v1
```

Para atualizar o deployment já realizado, use o comando `apply`:

```bash
kubectl apply -f deployment.yaml
```
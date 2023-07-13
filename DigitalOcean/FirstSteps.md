## First steps

1. Install kubectl
2. Install doctl (Tool from digital ocean cli) 

```bash
sudo snap install doctl
```
3. create paht .config and connect doctl with token API
```bash
doctl auth init
```
4. connect kube config with doctl
```bash
sudo snap connect doctl:kube-config
```
commands examples:
```bash
doctl kubernetes cluster kubeconfig save cluster1
```
obs.: create .kube (mkdir .kube)

Other commands:
```bash
doctl kubernetes cluster list
```
```bash
doctl kubernetes node-pool list cluster1
```
```bash
kubectl cluster-info
```

> enable auto completion https://github.com/digitalocean/doctl#linux-auto-completion
```bash
echo "source <(doctl completion bash)" >> .profile
source .profile
```

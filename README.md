# k3d-scripts

Repositório para scripts de exmplos de uso do K3D

## Instalação

Via curl:

``` bash
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

Ref.: https://k3d.io/v5.6.0/#installation

## Comando básicos

Cria um novo cluster com 3 nós, 2 workers e 1 control-plane, configurando as portas 30000 do kubernetes para a porta 8000 do host e setando o LoadBalancer.

``` bash
k3d cluster create -p "8000:30000@loadbalancer" --agents 2
```

Lista os clusters existentes

``` bash
k3d cluster list
```

## Exemplo de configuração do nginx

Executar os scripts na pasta ./samples-scripts/nginx para criação do deploy e da service.

``` bash
kubectl apply -f samples-scripts/nginx/deployment.yaml
kubectl apply -f samples-scripts/nginx/service.yaml
```

Acessar a URL http://localhost:8000 no host para teste do nginx.
---
title: "EKS"
date: 2018-11-22 
weight: 1
draft: false
---

## EKS Instalação e Configuração 

#### Sobre

Página principal do produto: 

#### Instalação 

#### Instalação EKSCTL 

Utilizando brew, instale o repositorio e depois instale o eksctl 

```
brew tap weaveworks/tap
brew install weaveworks/tap/eksctl
```
Verifique a instalação:

````
eksctl version
````


#### Criação do cluster EKS

Criação do cluster EKS
```
eksctl create cluster --name=eksworkshop-eksctl --nodes=3 --node-ami=auto --region=${AWS_REGION}
```

Verifique o cluster e check os nodes
```
kubectl get nodes
```

#### Vídeos

#### Documentos

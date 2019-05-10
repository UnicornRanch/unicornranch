---
title: "EKS"
date: 2019-05-02 
weight: 1
draft: false
---
#### Criação do cluster EKS

Criação do cluster EKS
```
eksctl create cluster --name=eksworkshop-eksctl --nodes=3 --node-ami=auto --region=${AWS_REGION}
```

Entre no console do CloudFormation e copie o ServiceRoleARN, iremos utilizar esse id no arquivo abaixo.

#### Configuração do KUBECTL 

Crie o arquivo aws-auth-cm.yaml
````
apiVersion: v1
kind: ConfigMap
metadata:
  name: aws-auth
  namespace: kube-system
data:
  mapRoles: |
    - rolearn: <COLOQUE O ID DO SERVICE ROLE ARN DO CLOUD FORMATION AQUI>
      username: system:node:{{EC2PrivateDNSName}}
      groups:
        - system:bootstrappers
        - system:nodes
````

Configure o KUBECTL utilizando arquivo criado acima
````
kubectl apply -f aws-auth-cm.yaml
````

Verifique se o kuibectl está funcionando e check os nodes
```
kubectl get nodes
```

#### Configure o Dashboard 

Instale o dashboard oficial
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml
```

Execute o proxy
````
kubectl proxy &
````

Pegue o token de segurança para acesso ao proxy
````
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep eks-admin | awk '{print $1}')
````

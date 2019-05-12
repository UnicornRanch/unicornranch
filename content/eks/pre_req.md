---
title: "Pré-requisitos"
date: 2019-05-09
weight: 1
draft: false
---
update: 2019-05-12

### Para MACOS

#### Instale KUBECTL 
`````
brew install kubectl
`````

#### Instale e configure o AWSCLI 

Baixe o bundle do AWSCLI do repositório oficial
````
curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
````

Descompacte o pacote
````
unzip awscli-bundle.zip
````

Instale utilizando o commando abaixo
````
sudo ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
````

Mais informação no [link](https://docs.aws.amazon.com/cli/latest/userguide/install-macos.html) 

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
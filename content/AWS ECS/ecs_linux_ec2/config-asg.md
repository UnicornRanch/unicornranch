---
title: "Configurando Launch Group"
date: 2019-11-12
weight: 2
draft: false
---
updated: 2019-11-12

#### Criação do ASG Launch Configuration

- Procure por uma imagem chamada ECS-Optmized e selecione essa imagem: 
![Connecting](/images/ecs/linux-ec2/asg-lc01.png)


- Selecione o tipo de instância:
![Connecting](/images/ecs/linux-ec2/asg-lc02.png)


- Click em "Advance Details" e declare o nome do cluster em User Data:
![Connecting](/images/ecs/linux-ec2/asg-lc03.png)

```
#!/bin/bash
echo ECS_CLUSTER=NOME_DO_CLUSTER >> /etc/ecs/ecs.config
```

- Selecione o Storage:
![Connecting](/images/ecs/linux-ec2/asg-lc04.png)

- Selecione o Security Group:
![Connecting](/images/ecs/linux-ec2/asg-lc05.png)

- Click em launch configuration:
![Connecting](/images/ecs/linux-ec2/asg-lc06.png)

- Selecione a public key:
![Connecting](/images/ecs/linux-ec2/asg-lc07.png)


#### Criação do ASG Launch Configuration


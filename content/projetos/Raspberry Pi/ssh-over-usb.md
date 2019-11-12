---
title: "SSH over USB"
date: 2019-11-11
weight: 1
draft: false
---
#### Esse procedimento só funciona com as seguintes raspberrypi disponíveis:
- Raspberry Pi Zero
- Raspberry Pi Zero W

#### Monte o SD no seu computador e acesse a raiz. 
- procure pelo /boot

#### Habilite o SSH
- para isso somente crie um arquivo em branco na raiz, como no exemplo abaixo:

```
touch /boot/ssh
```

#### Adicione o driver a configuração do device tree

- edite o arquivo config.txt:

```
vi /boot/config.txt
```

- acrescente a seguinte linha:

```
dtoverlay=dwc2
```

#### Carregue o módulo no boot

- edite o arquivo cmdline.txt

```
vi /boot/cmdline.txt
```
- depois do rootwait, adicione, somente com espaço e sem virgulas, a chamada para os seguintes módulos:

```
modules-load=dwc2,g_ether
```
#### Para logar no Raspberry
- coloque de volta o SD no raspberry 
- conecte o cabo usb na porta denominada USB (e não na porta POWER)
- abra o terminal e digite:

```
ssh-keygen -R raspberrypi.local
ssh pi@raspberrypi.local
```



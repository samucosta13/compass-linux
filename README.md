# Documentação

> Atividade de Linux da trilha DevSecOps do programa de bolsas da Compass.uol

## Passo a passo

* Subir uma *Virtual Machine* (VM)
* Configurar a interface de rede para o modo Bridge
* Instalar um servidor Oracle Linux 8.6 nela
* Configurar uma relação de confiança entre a VM criada e um clone dela
* Versionar os diretórios e arquivos criados ou editados nesse processo
* Criar uma apresentação de slides com os comandos e as etapas da atividade
* Documentar o trabalho como um todo

## *Virtual Machine* (VM)

* Nome da VM: host_server
* Memory: 1024 MB
* *Virtual Hard Disk* (VHD): 30 GB, dinamicamente alocado
* Ordem de *boot*: disco óptico, disco rígido
* Processador: 1 núcleo do processador Core i3 (2,3 GHz) da máquina física
* Interface de rede: wlp3s0 em modo Bridge
* SO: Oracle Linux 8.6 (64-bit)

## Sistema operacional do servidor

### Instalação

* Instalação no modo *Minimal Install*
* Idioma: English (United Kingdom)
* Teclado: Portuguese (Brazil)
* Fuso horário: Americas/Sao Paulo timezone
* *hostname*: localhost.localdomain (alterei o nome do host para **server** depois)
* Usuários: root e samuel (*maked administrator*)
* Rede: Ethernet (enp0s3) connected

### Particionamento

> A alocação automática feita durante a instalação

> Considere o servidor apenas com os arquivos nativos

* **/boot** - 213 MB
* **/** - 2.2 GB
* **/home** - 16 KB

## Relação de confiança 

> Autenticação com chave ***ecdsa*** via conexão SSH

> Para realizar o acesso via SSH, a VM host_server foi clonada. O clone foi nomeado de host_copy e recebeu um endereço MAC diferente

* No host **server** e no host **copy** foram geradas chaves privadas e públicas do tipo **ecdsa**
* As chaves públicas foram encaminhadas de um host para o outro, via SSH
* A conexão segura foi feita com sucesso! 

> Neste repositório encontram-se os diretórios do server e do copy que contém os arquivos do SSH, onde se encontram as chaves públicas e privadas de cada um, bem como a lista de hosts conhecidos

## Apresentação de slides

* Após versionar o conteúdo gerado pelo acesso remoto com SSH, a atividade propõe discorrer sobre alguns comandos, com auxílio de uma apresentação de slides.
* A apresentação, em PDF, não está disponível neste repositório, por ser um material restrito aos participantes do Programa de Bolsas da Compass.uol. Porém, seguem as principais referências que utilizei para a pesquisa dos comandos.

  * [Configuring basic system settings.](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/configuring_basic_system_settings/index#doc-wrapper)
  * [Managing partitions in Linux with fdisk.](https://www.redhat.com/sysadmin/partitions-fdisk)
  * [O que é um endereço MAC?](https://help.gnome.org/users/gnome-help/stable/net-macaddress.html.pt)
  * [Yum Command Cheat Sheet for Red Hat Enterprise Linux.](https://access.redhat.com/articles/yum-cheat-sheet)

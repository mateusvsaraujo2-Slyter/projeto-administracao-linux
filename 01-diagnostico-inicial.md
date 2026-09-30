# Diagnostico inicial do Servidor Techlab

## Distribuição GNU/Linux

![Imagem 01 do projeto](img/01-img-01.png)
**Sistema operacional:** Debian GNU/Linux 13 (trixie)
**Versão completa:** 13.7 
**Explicação:** Essas informações nos permitem identificar o nome da distribuição
bem como a sua versão completa instalada.

## Kernel 
**Hostname:** debian-lab-1
**Release do Kernel:** 6.12.10+deb13-amd64
**Arquitetura:** x86_64

Na imagem tbm podemos ver informações sobre o kernel dos sistema, o kernel é o responsavel por gerenciar alguns recursos do sistema, é importante não confundir A distribuição com o kernel apesar de trabalharem juntas não são a mesma coisa, o kernel possui sua propria versão, na imagem também podemos ver sua arquitetura e o hostname da VM em questão.

## Tempo de atividade
**Comando Uptime** 
[Imagem 02 do projeto](img/01-img-02.png)
Ao executar o comando uptime podemos acessar informações como há quanto tempo a maquina está ligada, o número de usuários e o load average que mostra a carga média de uso do sistema

**Tempo de atividade:** 6 horas e 30 minutos
**Usuários/sessões:** 2
**Load average:8** 0.00, 0.00, 0.00


## Memória RAM e Swap
**Comando:** free -h
[Imagem 03 do projeto](img/01-img-3.png)
Esse comando permitiu visualizar informações sobre a memória RAM e swap, na imagem podemos ver  a  memória total disponível e a swap
que é um local onde é armazenada uma parte da memória RAM  acelerar o sistema essa memória pode ser recuperada caso necessário

**RAM total:** 3.8GiB
**RAM utilizada:** 1.1 GiB
**RAM livre:** 2.1 GiB
**RAm disponivel:** 2.7 GiB
**Swap total:** 1.6 GiB
**Swap utilizada:** 0B

## Sistemas de arquivos
**Comando:** df-h
[Imagem 04 do projeto](img/01-img-04.png)
Esse comando permite visualizar o uso de espaço de sistemas de arquivo montados.
podemos ver o disco principal e o particionamento bem como o tamanho total do disco e seu uso

Dispositivo: /dev/sda1
Tamanho: 29G
Utilizado: 5.0G
Disponível: 23G
Uso: 19%
Montado em: /

## Dispositivos de armazenamento
**Comando lsblk**
[Imagem 05 do projeto](img/01-img-05.png)

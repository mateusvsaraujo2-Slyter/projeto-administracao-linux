# Parte 4 - Permissões e controles de acesso

## Objetivo 

Configurar as permissões dos diretórios da TechLab para que cada equipe tenha acesso adequado aos seus arquivos, impedindo alterações por usuários não autorizados.

Também foram utilizados grupos, permissões numéricas e simbólicas, umask e setgid para controlar a criação e o compartilhamento de arquivos. 

## 1. Diretório desenvolvimento
 
**Grupo proprietário:** ` desenvolvimento` 

**Permissão:** ` 775` 

**Comandos utilizados:** 

```bash
sudo chgrp desenvolvimento /srv/techlab/desenvolvimento
sudo chmod 775 /srv/techlab/desenvolvimento
sudo chmod g+s /srv/techlab/desenvolvimento
```
Sudo chrgp permite mudar grupo proprietário do diretório  no caso alterando root para desenvolvimento

A permissão 775 permite o proprietário e grupo terem todas as permissões enquanto permite a outros apenas leitura e execução sem escrita.

Sudo chmod g+s adiciona o setgid que faz com que os diretório que serão criados no diretório herdem as permissões do grupo

## 2. Diretório suporte 
 
**Grupo proprietário**  Suporte

**Permissão** ` 775` 

**Comandos utilizados** 

```bash
sudo chgrp suporte /srv/techlab/suporte
sudo chmod 775 /srv/techlab/suporte
sudo chmod g+s /srv/techlab/suporte 
``` 
Os comandos assim como em desenvolvimento permitiram alterar o grupo proprietário e definir as permissões e adicionar o setgid

## 3. Diretório administração

**Grupo proprietário:** `administração`

**Permissão:** `770` 

**Comandos utilizados:**

sudo chgrp administracao /srv/techlab/administracao
sudo chmod 770 /srv/techlab/administracao
sudo chmod g+s /srv/techlab/admministracao

Nesse comando também temos a alteração do grupo proprietário e adicionamos o setgid como nos outros grupos mas aqui temos uma importante diferença em relação as permiçoes nesse caso "outros" não tem nenhuma permissãodeixando o grupo administração apenas acessivél ao proprietário e membros do grupo com permissão.

## 4. Diretório compartilhado 

**Grupo proprietário:** `compartilhado`

**Permissão:** `775`

**Usuários do grupo compartilhado:**

- `dev01` 
- `dev02`
- `sup01`
- `sup02` 

**Comandos utilizados**

```bash
sudo groupadd compartilhado

sudo usermod -aG compartilhado dev01
sudo usermod -aG compartilhado dev02
sudo usermod -aG compartilhado sup01
sudo usermod -aG compartilhado sup02

sudo chgrp compartilhado /srv/techlab/compartilhado
sudo chmod 775 /srv/techlab/compartilhado
sudo chmod g+s /srv/techlab/compartilhado
```

O grupo compartilhado foi criado para que  as  equipes de desenvolvimento e suporte consigam trabalhar juntaem um grupo específico para isso, o usemod -aG adicionou os usuários ao grupo sem interferir nos seus grupos primários e não usamos 777 para as permissões para manter a segurança do grupo deixando "outros" apenas com permissões de execução e leitura.

## 5. umask 

Uma umask define quais permissões serão retiradas das permissões base quando novos arquivos e diretórios são criados, por exemplo um arquivo utiliza uma base de 666 então se a umask for 022 o proprietário continua com as mesmas permissões mas mas grupos e outros ficam somente com leitura.
Já os diretórios utilizam normalmente a base 777 e com a mesma umask criamos as permissões 755  

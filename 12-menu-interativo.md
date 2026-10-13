# Parte 12 — Menu Interativo em Shell Script

## 1. Objetivo

Desenvolver um menu interativo em Bash para facilitar a execução de tarefas administrativas no servidor TechLab.

## 2. Ambiente

- Sistema operacional: Debian GNU/Linux 13
- Interpretador: Bash
- Editor: Vim
- Script: `/srv/techlab/scripts/menu-techlab.sh`

## 3. Funcionalidades implementadas

O menu permite:

1. Consultar informações do servidor;
2. Verificar a utilização da memória RAM;
3. Consultar a quantidade de erros do log;
4. Gerar o relatório do servidor;
5. Encerrar o programa.

Também foi implementado um tratamento para opções inválidas.

## 4. Conceitos utilizados

- `echo`: apresenta mensagens no terminal.
- `read`: recebe a opção digitada pelo usuário.
- `case`: seleciona a ação correspondente.
- `while`: mantém o menu em execução.
- `break`: encerra a repetição.
- `if/else`: verifica a existência do arquivo de log.

## 5. Evidências

### Evidência 01 — Código-fonte

![Código do menu interativo](img/12-img-01.png)

### Evidência 02 — Execução das funcionalidades

![Execução das opções do menu](img/12-img-02.png)

### Evidência 03 — Geração do relatório e encerramento

![Relatório e encerramento do programa](img/12-img-03.png)

## 6. Testes realizados

Foram testadas as opções 1, 2, 3, 4, 9 e 0.

O menu apresentou corretamente as informações solicitadas, identificou 10 registros de erro, executou o script de relatório e tratou uma opção inválida.

A estrutura de repetição manteve o menu disponível até a seleção da opção 0.

## 7. Conclusão

O menu interativo foi implementado e testado com sucesso.

A atividade permitiu aplicar estruturas condicionais e de repetição em Bash, além de integrar funcionalidades desenvolvidas anteriormente no projeto TechLab.

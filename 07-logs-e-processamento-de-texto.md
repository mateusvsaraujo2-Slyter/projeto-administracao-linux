# Parte 7 — Logs e processamento de texto

## Objetivo

Criar e analisar um arquivo de log fictício utilizando comandos de processamento de texto do GNU/Linux.

## Arquivo utilizado

`/srv/techlab/acessos.log`

O arquivo possui 30 registros no formato:

`DATA HORA USUÁRIO AÇÃO RESULTADO`

Exemplo:

`2026-10-05 15:05:27 admin01 BACKUP ERRO`

## Principais comandos

Visualização:

`cat`, `less`, `head` e `tail`

Pesquisa:

`grep`, `grep -E` e `egrep`

Processamento:

`cut`, `awk`, `wc`, `sort` e `uniq`

Comparação:

`diff`

Também foram utilizados pipes (`|`) e redirecionamentos (`>` e `>>`) para combinar comandos e salvar resultados.

## Exemplo de análise

Contagem de registros por usuário:

`awk '{print $3}' /srv/techlab/acessos.log | sort | uniq -c`

## Resultado

Foi possível pesquisar, filtrar, ordenar, contar e comparar informações presentes no arquivo de log utilizando ferramentas nativas do GNU/Linux.

# Parte 11 — Automação de Relatórios com Shell Script

## 1. Objetivo

Desenvolver um script Bash capaz de coletar automaticamente informações do servidor Debian e gerar um relatório em formato Markdown.

A atividade tem como objetivo praticar:

- Comandos de administração GNU/Linux;
- Variáveis e substituição de comandos;
- Estruturas condicionais `if/else`;
- Redirecionamento de saída;
- Leitura e análise de arquivos de log;
- Automação de tarefas administrativas.

## 2. Ambiente utilizado

| Item | Descrição |
|---|---|
| Sistema operacional | Debian GNU/Linux 13 |
| Servidor | debian-lab-1 |
| Interpretador | Bash |
| Editor de texto | Vim |
| Script | `/srv/techlab/scripts/relatorio-servidor.sh` |
| Relatório gerado | `/tmp/relatorio-techlab.md` |
| Arquivo de log | `/srv/techlab/acessos.log` |

## 3. Desenvolvimento do script

Foi desenvolvido um script para coletar as seguintes informações:

- Data e hora da execução;
- Nome do servidor;
- Versão do kernel;
- Tempo de atividade;
- Utilização da memória RAM;
- Utilização dos sistemas de arquivos;
- Quantidade de registros de erro no arquivo de log.

O script utiliza uma estrutura condicional para verificar a existência do arquivo `acessos.log` antes de realizar a contagem dos erros.

As informações coletadas são organizadas em seções Markdown e gravadas automaticamente em um arquivo de relatório.

### Evidência 01 — Código-fonte

A imagem apresenta o script desenvolvido no editor Vim, incluindo os comandos utilizados, a estrutura condicional e o redirecionamento da saída.

![Código do script Bash](img/11-img-01.png)

## 4. Validação e execução

Inicialmente, foi realizada a verificação sintática do script:

```bash
bash -n /srv/techlab/scripts/relatorio-servidor.sh
```

Em seguida, o script foi executado:

```bash
bash /srv/techlab/scripts/relatorio-servidor.sh
```

Para verificar a existência do relatório gerado:

```bash
ls -lh /tmp/relatorio-techlab.md
```

### Evidência 02 — Validação e execução

A imagem demonstra os comandos utilizados para validar e executar o script, além de verificar a criação do arquivo Markdown.

![Validação e execução do script](img/11-img-02.png)

## 5. Resultado obtido

Após a execução, o relatório foi consultado utilizando:

```bash
cat /tmp/relatorio-techlab.md
```

O arquivo apresentou as informações do servidor, incluindo:

- Hostname: `debian-lab-1`;
- Kernel: `6.12.107+deb13-amd64`;
- Memória RAM total: aproximadamente 3,8 GiB;
- Partições e pontos de montagem;
- Quantidade de erros identificados: **10**.

### Evidência 03 — Relatório gerado

A imagem demonstra o conteúdo do relatório Markdown, incluindo as informações de hardware, sistema operacional e análise de logs.

![Relatório Markdown gerado](img/11-img-03.png)

## 6. Verificação dos registros de erro

Para conferir a quantidade de erros presente no arquivo de log, foi utilizado:

```bash
grep -c 'ERRO$' /srv/techlab/acessos.log
```

Para consultar a quantidade registrada no relatório:

```bash
grep 'Quantidade de erros:' /tmp/relatorio-techlab.md
```

Os resultados apresentaram a mesma quantidade: **10 erros**.

### Evidência 04 — Conferência dos registros

A imagem apresenta a comparação entre a contagem realizada diretamente no arquivo de log e a informação gerada pelo script.

![Verificação dos registros de erro](img/11-img-04.png)

## 7. Conhecimentos adquiridos

Durante o desenvolvimento desta atividade, foram praticados conceitos importantes de Shell Script:

- **`echo`:** exibição de mensagens e formatação do relatório;
- **`$(...)`:** captura da saída de comandos em variáveis;
- **`if/else`:** execução condicional;
- **`grep -c`:** contagem de registros;
- **`>`:** redirecionamento e sobrescrita de arquivos;
- **`bash -n`:** verificação sintática do script;
- **Markdown:** organização e apresentação das informações coletadas.

## 8. Conclusão

A atividade demonstrou como utilizar Shell Script para automatizar tarefas de administração de sistemas GNU/Linux.

O script desenvolvido reúne informações relevantes do servidor em um único relatório, reduzindo a necessidade de executar manualmente cada comando.

A geração do arquivo Markdown também permite registrar e consultar os resultados das verificações realizadas no ambiente TechLab.

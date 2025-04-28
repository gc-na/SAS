<!--
Meta Description: # IF: Comando Condicional no SAS ## Sinopse O comando "IF" no SAS é uma instrução fundamental que permite a execução de condicionais, possibilitando a...
Meta Keywords: sas, que, comando, dados, condições
-->

# IF: Comando Condicional no SAS

## Sinopse
O comando "IF" no SAS é uma instrução fundamental que permite a execução de condicionais, possibilitando a manipulação e a filtragem de dados com base em critérios específicos.

## Documentação
O comando IF no SAS é utilizado para executar instruções condicionais em um passo DATA ou um PROC. Ele permite que você teste uma condição e, com base no resultado, execute um bloco de código específico. A sintaxe básica do comando IF é:

```sas
IF condição THEN ação;
```

### Propósito
O propósito do comando IF é controlar o fluxo de execução do código SAS, permitindo que certas ações sejam tomadas somente quando condições específicas são atendidas.

### Uso
O comando IF pode ser utilizado em várias situações, como:
- Atribuição de valores a variáveis com base em condições.
- Filtragem de dados durante a leitura de um conjunto de dados.
- Criação de novas variáveis que dependem de condições lógicas.

### Detalhes
- O comando IF pode ser utilizado em combinação com operadores lógicos (como AND, OR) para avaliar múltiplas condições.
- Pode ser aninhado, permitindo a execução de múltiplas condições em sequência.
- A instrução ELSE pode ser utilizada para definir uma alternativa quando a condição IF não é verdadeira.

## Exemplos
### Exemplo 1: Atribuição Condicional
```sas
data exemplo1;
    set dados;
    if idade < 18 then categoria = 'Menor';
    else categoria = 'Adulto';
run;
```

### Exemplo 2: Filtragem de Dados
```sas
data exemplo2;
    set dados;
    if salario > 5000 then output;
run;
```

### Exemplo 3: Aninhamento de IF
```sas
data exemplo3;
    set dados;
    if idade < 18 then grupo = 'Jovem';
    else if idade < 65 then grupo = 'Adulto';
    else grupo = 'Idoso';
run;
```

## Explicação
Um erro comum ao usar o comando IF no SAS é a falta de um bloco ELSE, que pode levar à atribuição de valores inesperados quando a condição não é atendida. Além disso, é importante lembrar que o SAS é sensível a espaços em branco e que a sintaxe correta deve ser seguida para evitar erros de execução. Outro ponto a ser considerado é a ordem das condições, já que o SAS avalia as instruções em sequência e executará o primeiro bloco que encontrar que satisfaça a condição.

## Resumo em Uma Linha
O comando IF no SAS é uma ferramenta essencial para a execução de lógica condicional, permitindo a manipulação flexível de dados com base em critérios definidos.
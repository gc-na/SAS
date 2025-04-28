<!--
Meta Description: # MERGE em SAS: Como Unir Conjuntos de Dados de Forma Eficiente ## Sinopse O comando MERGE no SAS é uma técnica poderosa para combinar dois ou mais co...
Meta Keywords: dados, merge, conjuntos, variáveis, sas
-->

# MERGE em SAS: Como Unir Conjuntos de Dados de Forma Eficiente

## Sinopse
O comando MERGE no SAS é uma técnica poderosa para combinar dois ou mais conjuntos de dados com base em variáveis comuns, permitindo a análise integrada de informações.

## Documentação
O comando MERGE é utilizado no SAS para combinar conjuntos de dados que compartilham uma ou mais variáveis-chave. Essa operação é essencial para consolidar informações de diferentes fontes e realizar análises mais completas.

### Propósito
O MERGE é projetado para unir datasets, facilitando a análise de dados relacionados. É especialmente útil em situações onde é necessário agregar informações de diferentes tabelas, como dados de vendas e dados de clientes.

### Uso
A sintaxe básica do comando MERGE é a seguinte:

```sas
DATA conjunto_unido;
    MERGE conjunto1 conjunto2;
    BY variavel_chave;
RUN;
```

- `conjunto_unido`: Nome do novo conjunto de dados resultante da união.
- `conjunto1` e `conjunto2`: Nomes dos conjuntos de dados a serem unidos.
- `variavel_chave`: A variável ou variáveis que servem como critério de união.

### Detalhes
- A operação MERGE deve ser precedida pelo comando DATA.
- É necessário que os conjuntos de dados estejam ordenados pela variável chave utilizada na união.
- O MERGE pode combinar mais de dois conjuntos de dados.
- Se houver variáveis com o mesmo nome em diferentes conjuntos de dados, o SAS manterá a variável do primeiro conjunto de dados listado, a menos que uma renomeação seja feita.

## Exemplos

### Exemplo Básico
Suponha que você tenha dois conjuntos de dados: `clientes` e `vendas`.

```sas
DATA clientes;
    INPUT id_cliente nome $;
    DATALINES;
1 Ana
2 Bruno
3 Carlos
;
RUN;

DATA vendas;
    INPUT id_cliente valor_venda;
    DATALINES;
1 100
2 200
3 150
;
RUN;

DATA dados_unidos;
    MERGE clientes vendas;
    BY id_cliente;
RUN;

PROC PRINT DATA=dados_unidos;
RUN;
```

Neste exemplo, os dados de clientes e vendas são unidos pelo identificador do cliente (`id_cliente`).

### Exemplo com Várias Variáveis
Se você tiver mais de uma variável chave, a sintaxe permanece semelhante:

```sas
DATA conjunto1;
    INPUT id_cliente id_pedido;
    DATALINES;
1 101
2 102
;
RUN;

DATA conjunto2;
    INPUT id_cliente id_pedido valor;
    DATALINES;
1 101 300
2 102 400
;
RUN;

DATA resultado_final;
    MERGE conjunto1 conjunto2;
    BY id_cliente id_pedido;
RUN;
```

## Explicação
### Armadilhas Comuns
- **Conjuntos não Ordenados**: O MERGE requer que os conjuntos de dados estejam ordenados pela(s) variável(is) chave. Use o procedimento SORT antes do MERGE para evitar erros.
  
- **Variáveis com o Mesmo Nome**: Se duas variáveis em diferentes conjuntos de dados tiverem o mesmo nome, o SAS manterá a primeira encontrada. Use o comando RENAME para evitar confusões.

- **Dados Ausentes**: Se um conjunto de dados não tiver correspondência para uma variável chave, o resultado terá valores ausentes (missing) para as variáveis desse conjunto.

### Notas Adicionais
- O MERGE é sensível ao tipo de dado das variáveis chave. Certifique-se de que ambas as variáveis sejam do mesmo tipo (numérico ou caractere).
- Para unir conjuntos de dados de forma mais complexa, considere o uso do SQL em SAS, que pode oferecer maior flexibilidade em certos casos.

## Resumo em Uma Frase
O comando MERGE em SAS é uma ferramenta essencial para combinar conjuntos de dados com base em variáveis comuns, facilitando análises integradas e abrangentes.
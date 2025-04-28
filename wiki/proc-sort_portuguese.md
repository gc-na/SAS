<!--
Meta Description: # PROC SORT: Ordenação de Dados no SAS ## Sinopse O PROC SORT é uma poderosa instrução do SAS utilizada para organizar dados em conjuntos de dados. El...
Meta Keywords: dados, proc, sort, que, exemplo
-->

# PROC SORT: Ordenação de Dados no SAS

## Sinopse
O PROC SORT é uma poderosa instrução do SAS utilizada para organizar dados em conjuntos de dados. Ele permite que os usuários classifiquem os dados de acordo com uma ou mais variáveis, facilitando a análise e a visualização dos dados.

## Documentação
### Propósito
A instrução PROC SORT é fundamental na preparação de dados para análise, pois garante que os dados estejam organizados de forma lógica e acessível. A ordenação é essencial em diversas etapas de análise de dados, como a fusão de conjuntos de dados e a criação de relatórios.

### Uso
A sintaxe básica do PROC SORT é a seguinte:

```sas
PROC SORT DATA=dataset OUT=sorted_dataset;
    BY variable(s);
RUN;
```

- **DATA=**: Especifica o conjunto de dados de entrada que será ordenado.
- **OUT=**: Define o nome do conjunto de dados ordenado que será gerado.
- **BY**: Indica a(s) variável(eis) que serão usadas para a ordenação. Você pode especificar múltiplas variáveis separadas por espaços.

### Detalhes
- O PROC SORT ordena os dados em ordem crescente por padrão. Para ordenação decrescente, adicione a palavra-chave `DESCENDING` antes da variável.
- O PROC SORT modifica o conjunto de dados original, a menos que você especifique um conjunto de dados de saída (OUT=).
- Variáveis com valores ausentes são posicionadas no início da lista quando ordenadas em ordem crescente e no final quando em ordem decrescente.

## Exemplos
### Exemplo Básico
```sas
DATA exemplo;
    INPUT nome $ idade;
    DATALINES;
    Carlos 30
    Ana 25
    Pedro 28
    Maria 22
    ;
RUN;

PROC SORT DATA=exemplo OUT=exemplo_ordenado;
    BY idade;
RUN;

PROC PRINT DATA=exemplo_ordenado;
RUN;
```
Neste exemplo, o conjunto de dados `exemplo` é ordenado pela variável `idade`, resultando no conjunto de dados `exemplo_ordenado`.

### Exemplo com Ordenação Decrescente
```sas
PROC SORT DATA=exemplo OUT=exemplo_ordenado_desc;
    BY DESCENDING idade;
RUN;

PROC PRINT DATA=exemplo_ordenado_desc;
RUN;
```
Aqui, os dados são ordenados pela variável `idade` em ordem decrescente.

## Explicação
### Armadilhas Comuns
- **Especificação de Ordenação**: Esquecer de incluir a opção `OUT=` pode resultar na modificação do conjunto de dados original, o que pode não ser desejado.
- **Duplicação de Dados**: O PROC SORT não remove duplicatas. Para isso, utilize a opção `NODUPKEY` se a intenção for manter apenas uma ocorrência de cada valor nas variáveis de ordenação.
- **Formato dos Dados**: Certifique-se de que as variáveis que você está usando para ordenar têm o formato correto; por exemplo, números armazenados como texto podem causar resultados inesperados.

## Resumo em Uma Linha
O PROC SORT é uma instrução do SAS que organiza conjuntos de dados com base em uma ou mais variáveis, facilitando a análise e a visualização dos dados.
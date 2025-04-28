<!--
Meta Description: # OUTPUT no SAS: Comando Essencial para Exportação de Dados ## Sinopse O comando OUTPUT no SAS é uma ferramenta poderosa utilizada para exportar e man...
Meta Keywords: dados, output, comando, para, sas
-->

# OUTPUT no SAS: Comando Essencial para Exportação de Dados

## Sinopse
O comando OUTPUT no SAS é uma ferramenta poderosa utilizada para exportar e manipular dados durante a execução de um processo, permitindo que os usuários salvem subconjuntos de dados e resultados intermediários de forma eficiente.

## Documentação
O comando OUTPUT no SAS é empregado principalmente em procedimentos (PROCs) e em data steps para direcionar a saída de dados para conjuntos de dados SAS. Ele permite que os usuários especifiquem quais observações devem ser gravadas em um conjunto de dados específico, oferecendo flexibilidade na manipulação e análise de dados.

### Propósito
O principal objetivo do comando OUTPUT é facilitar a gravação seletiva de observações em um conjunto de dados, o que é especialmente útil quando se trabalha com grandes volumes de dados ou quando se deseja criar relatórios e análises personalizadas.

### Uso
O comando OUTPUT pode ser utilizado dentro de um DATA step ou em um PROC, sendo a sintaxe básica a seguinte:

```sas
OUTPUT <nome_do_conjunto>;
```

Onde `nome_do_conjunto` é o identificador do conjunto de dados onde as observações deverão ser salvas.

### Detalhes
- **Data Step**: Dentro de um DATA step, o comando OUTPUT pode ser utilizado para salvar observações específicas conforme condições lógicas.
- **PROC**: Em procedimentos como PROC SORT ou PROC MEANS, o OUTPUT pode ser usado para salvar resultados resumidos ou ordenados em novos conjuntos de dados.
- **Múltiplas Saídas**: É possível usar múltiplos comandos OUTPUT para gravar em diferentes conjuntos de dados a partir do mesmo passo de dados.

## Exemplos
### Exemplo 1: Usando OUTPUT em um DATA Step
```sas
data novo_conjunto;
    set conjunto_original;
    if idade > 30 then output novo_conjunto;
run;
```

Neste exemplo, apenas as observações onde a idade é superior a 30 são gravadas no `novo_conjunto`.

### Exemplo 2: Usando OUTPUT em PROC MEANS
```sas
proc means data=conjunto_original noprint;
    var salario;
    output out=media_salarios mean=media;
run;
```

Aqui, a média dos salários é calculada e armazenada em um novo conjunto de dados chamado `media_salarios`.

## Explicação
### Armadilhas Comuns
- **Uso do OUTPUT sem condições**: Se o OUTPUT for utilizado sem uma condição clara, pode resultar em um conjunto de dados vazio ou em duplicações indesejadas.
- **Falta de Nome do Conjunto**: Não especificar um nome para o conjunto de dados no comando OUTPUT resultará em erro de execução.
- **Confusão com outros comandos**: É importante distinguir o OUTPUT do comando PRINT, pois o OUTPUT armazena dados, enquanto o PRINT exibe os dados.

## Resumo em Uma Frase
O comando OUTPUT no SAS é fundamental para a exportação e manipulação de dados, permitindo que os usuários salvem observações selecionadas em conjuntos de dados específicos durante a análise.
<!--
Meta Description: # OUTPUT en SAS: Comando y Funcionalidad Esencial para la Generación de Resultados ## Sinopsis El comando OUTPUT en SAS se utiliza para controlar la s...
Meta Keywords: resultados, datos, output, conjunto, sas
-->

# OUTPUT en SAS: Comando y Funcionalidad Esencial para la Generación de Resultados

## Sinopsis
El comando OUTPUT en SAS se utiliza para controlar la salida de datos generados por una operación o un procedimiento, permitiendo al usuario personalizar cómo y dónde se almacenan los resultados.

## Documentación
El comando OUTPUT en SAS permite a los programadores especificar qué observaciones se deben escribir en un conjunto de datos de salida. Es particularmente útil en procedimientos como PROC SORT, PROC MEANS y PROC REG, donde es necesario guardar resultados intermedios o finales.

### Propósito
El propósito principal del comando OUTPUT es proporcionar un mecanismo flexible para la gestión de resultados intermedios o finales en un conjunto de datos. Esto es crucial para aquellos que analizan grandes volúmenes de datos y desean conservar resultados específicos para análisis futuros o reportes.

### Uso
El comando OUTPUT se utiliza dentro de un bloque de código SAS donde se ejecuta un procedimiento. La sintaxis básica es:

```
OUTPUT <nombre_del_conjunto_de_datos>;
```

Donde `nombre_del_conjunto_de_datos` es el nombre del conjunto donde se almacenarán los resultados.

### Detalles
- El comando OUTPUT se puede usar en combinación con la opción `WHERE` para filtrar las observaciones que se desean guardar.
- Puedes especificar múltiples conjuntos de datos en un solo comando, lo que permite una versatilidad adicional.
- Es importante recordar que, al usar OUTPUT, las observaciones solo se escribirán en el conjunto de datos cuando se cumplan las condiciones especificadas.

## Ejemplos
### Ejemplo 1: Guardar resultados de PROC MEANS

```sas
proc means data=mi_dataset noprint;
   var ingreso;
   output out=resultados mean=media_ingreso;
run;
```

En este ejemplo, se calcula la media de la variable `ingreso` y se guarda en un nuevo conjunto de datos llamado `resultados`.

### Ejemplo 2: Filtrar resultados con OUTPUT

```sas
data resultados;
   set mi_dataset;
   if ingreso > 1000;
   output;
run;
```

Aquí, solo se guardan las observaciones donde `ingreso` es mayor a 1000 en el conjunto de datos `resultados`.

## Explicación
Al usar OUTPUT, es importante tener en cuenta que:
- Los resultados se almacenan solo si el paso de datos actual se ejecuta sin errores.
- Si no se especifica un conjunto de datos, SAS generará un conjunto de datos por defecto llamado `_LAST_`.
- Un error común es olvidar incluir condiciones en el bloque de datos, lo que puede resultar en un conjunto de datos de salida que no refleja las observaciones deseadas.

## Resumen en una línea
El comando OUTPUT en SAS permite personalizar y controlar la salida de datos generados en procedimientos, facilitando la gestión de resultados específicos.
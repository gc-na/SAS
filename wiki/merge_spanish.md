<!--
Meta Description: # MERGE en SAS: Combina Datos de Múltiples Conjuntos ## Sinopsis El comando `MERGE` en SAS se utiliza para combinar dos o más conjuntos de datos en un...
Meta Keywords: datos, conjuntos, merge, los, sas
-->

# MERGE en SAS: Combina Datos de Múltiples Conjuntos

## Sinopsis
El comando `MERGE` en SAS se utiliza para combinar dos o más conjuntos de datos en uno solo, basándose en una o más variables clave. Esta operación es esencial para el análisis de datos, ya que permite consolidar información dispersa en diferentes fuentes.

## Documentación
### Propósito
El propósito del comando `MERGE` es unir conjuntos de datos que comparten variables comunes, facilitando así la creación de un conjunto de datos más completo y coherente. Esto es especialmente útil cuando se trabaja con múltiples archivos de datos que contienen información relacionada.

### Uso
La sintaxis básica del comando `MERGE` es la siguiente:

```sas
DATA conjunto_final;
    MERGE conjunto1 conjunto2;
    BY variable_clave;
RUN;
```

- `conjunto_final`: nombre del nuevo conjunto de datos resultante.
- `conjunto1`, `conjunto2`: nombres de los conjuntos de datos que se están combinando.
- `variable_clave`: la variable o variables por las que se realiza la combinación.

### Detalles
1. **Ordenación**: Antes de utilizar `MERGE`, los conjuntos de datos deben estar ordenados por la variable o variables clave. Esto se logra usando el procedimiento `SORT`.
  
2. **Tipos de combinación**: SAS permite combinaciones de uno a uno (donde cada clave es única en ambos conjuntos) y uno a muchos (donde una clave en un conjunto puede tener múltiples entradas en el otro).

3. **Manejo de observaciones no coincidentes**: Cuando las claves no coinciden, SAS asigna valores faltantes a las variables que no tienen correspondencia en uno de los conjuntos.

## Ejemplos
### Ejemplo 1: Combinación básica
```sas
/* Ordenar los conjuntos de datos */
PROC SORT DATA=conjunto1; BY id; RUN;
PROC SORT DATA=conjunto2; BY id; RUN;

/* Combinar los conjuntos de datos */
DATA conjunto_final;
    MERGE conjunto1 conjunto2;
    BY id;
RUN;
```

### Ejemplo 2: Combinación con múltiples claves
```sas
/* Ordenar los conjuntos de datos */
PROC SORT DATA=conjunto1; BY id fecha; RUN;
PROC SORT DATA=conjunto2; BY id fecha; RUN;

/* Combinar los conjuntos de datos */
DATA conjunto_final;
    MERGE conjunto1 conjunto2;
    BY id fecha;
RUN;
```

## Explicación
Al usar `MERGE`, es importante tener en cuenta ciertos aspectos:
- **Orden de los conjuntos**: La falta de ordenamiento previo puede resultar en un conjunto de datos incorrecto o inesperado.
- **Duplicados**: Si hay duplicados en las variables clave, el resultado puede no ser el deseado, ya que se generarán múltiples combinaciones.
- **Valores faltantes**: Al combinar, es posible que algunas variables no se llenen debido a la ausencia de coincidencias en los conjuntos originales.

## Resumen en una línea
El comando `MERGE` en SAS permite combinar múltiples conjuntos de datos en uno solo, utilizando variables clave para consolidar información relacionada.
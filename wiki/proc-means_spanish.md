<!--
Meta Description: # PROC MEANS en SAS: Análisis Estadístico Descriptivo ## Sinopsis PROC MEANS es un procedimiento en SAS que se utiliza para calcular estadísticas desc...
Meta Keywords: proc, means, datos, las, estadísticas
-->

# PROC MEANS en SAS: Análisis Estadístico Descriptivo

## Sinopsis
PROC MEANS es un procedimiento en SAS que se utiliza para calcular estadísticas descriptivas, como la media, la mediana, la desviación estándar, los percentiles y otros resúmenes de datos numéricos en conjuntos de datos.

## Documentación
### Propósito
El procedimiento PROC MEANS está diseñado para proporcionar un análisis estadístico básico de conjuntos de datos. Es ampliamente utilizado para resumir datos y obtener medidas de tendencia central y dispersión.

### Uso
La sintaxis básica de PROC MEANS es la siguiente:

```sas
PROC MEANS DATA=nombre_del_dataset;
   VAR variable1 variable2 ...;
   CLASS variable_clasificadora;
   OUTPUT OUT=nombre_del_output
          MEAN=media STD=desviacion;
RUN;
```

- **DATA**: Especifica el conjunto de datos que se va a analizar.
- **VAR**: Indica las variables numéricas sobre las que se calcularán las estadísticas.
- **CLASS**: (opcional) Permite clasificar los resultados según una o más variables categóricas.
- **OUTPUT**: (opcional) Permite guardar las estadísticas calculadas en un nuevo conjunto de datos.

### Detalles
PROC MEANS puede calcular varias estadísticas, incluidas:
- MEAN: media aritmética.
- MEDIAN: mediana.
- STD: desviación estándar.
- MIN: mínimo.
- MAX: máximo.
- N: número de observaciones.

El procedimiento también permite personalizar los resultados con opciones como `NOPRINT`, que suprime la salida en el log, y `FORMAT`, que aplica formatos específicos a las estadísticas calculadas.

## Ejemplos
### Ejemplo 1: Cálculo de estadísticas básicas
```sas
PROC MEANS DATA=mi_dataset;
   VAR ingreso edad;
RUN;
```
Este ejemplo calcula la media, la desviación estándar, el mínimo y el máximo de las variables `ingreso` y `edad` en el conjunto de datos `mi_dataset`.

### Ejemplo 2: Uso de la opción CLASS
```sas
PROC MEANS DATA=mi_dataset;
   CLASS genero;
   VAR ingreso;
RUN;
```
Aquí se calculan las estadísticas del ingreso agrupadas por la variable `genero`.

### Ejemplo 3: Guardar resultados en un nuevo dataset
```sas
PROC MEANS DATA=mi_dataset OUTPUT OUT=estadisticas
          MEAN=media_ingreso MEDIAN=mediana_ingreso;
   VAR ingreso;
RUN;
```
Este ejemplo guarda la media y la mediana de `ingreso` en un nuevo conjunto de datos llamado `estadisticas`.

## Explicación
Al utilizar PROC MEANS, es importante tener en cuenta:
- **Valores perdidos**: Las observaciones con valores faltantes en las variables especificadas no se incluyen en el cálculo de estadísticas.
- **Datos categóricos**: PROC MEANS solo trabaja con variables numéricas; si se especifican variables categóricas en la declaración VAR, se generará un error.
- **Salida**: Si el conjunto de datos es grande, la salida puede ser extensa. Se recomienda usar la opción `NOPRINT` si solo se desean guardar los resultados.
- **Optimización**: Utilizar las opciones de `OUTPUT` puede ser útil para el análisis posterior de los resultados sin necesidad de volver a calcular las estadísticas.

## Resumen en Una Línea
PROC MEANS en SAS es una herramienta poderosa para calcular estadísticas descriptivas de datos numéricos, permitiendo un análisis rápido y eficiente.
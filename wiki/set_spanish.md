<!--
Meta Description: # Comando SET en SAS: Uso y Ejemplos ## Sinopsis El comando SET en SAS es utilizado para leer datos de un conjunto de datos existente y cargarlos en e...
Meta Keywords: datos, conjunto, set, sas, conjuntos
-->

# Comando SET en SAS: Uso y Ejemplos

## Sinopsis
El comando SET en SAS es utilizado para leer datos de un conjunto de datos existente y cargarlos en el espacio de trabajo para su posterior manipulación y análisis. Este comando es fundamental en el proceso de gestión de datos y se utiliza en múltiples contextos dentro de la programación SAS.

## Documentación
El comando SET se utiliza dentro de un paso de datos (DATA step) para asignar un conjunto de datos existente a una nueva variable o conjunto de datos. Su propósito principal es permitir la manipulación de datos de forma eficiente, ya sea para la creación de nuevos conjuntos de datos, la modificación de los existentes o la combinación de múltiples conjuntos de datos.

### Propósito
- Leer datos de un conjunto de datos existente.
- Permitir la creación de nuevas variables o el procesamiento de datos.
- Facilitar la combinación de múltiples conjuntos de datos.

### Uso
La sintaxis básica del comando SET es la siguiente:

```sas
DATA nuevo_conjunto;
    SET conjunto_existente;
    /* Operaciones adicionales */
RUN;
```

### Detalles
- `nuevo_conjunto`: Nombre del conjunto de datos que se creará.
- `conjunto_existente`: Nombre del conjunto de datos que se leerá.
- El comando SET puede utilizarse para leer múltiples conjuntos de datos al mismo tiempo, separando los nombres de los conjuntos por espacios.

## Ejemplos
### Ejemplo 1: Lectura de un conjunto de datos
```sas
DATA empleados;
    SET datos_empleados;
RUN;
```
En este ejemplo, se crea un nuevo conjunto de datos llamado `empleados` que contiene todos los registros del conjunto `datos_empleados`.

### Ejemplo 2: Combinación de conjuntos de datos
```sas
DATA todos_empleados;
    SET datos_empleados1 datos_empleados2;
RUN;
```
Aquí, se combinan dos conjuntos de datos, `datos_empleados1` y `datos_empleados2`, en un nuevo conjunto llamado `todos_empleados`.

### Ejemplo 3: Creación de nuevas variables
```sas
DATA empleados_modificados;
    SET datos_empleados;
    sueldo_anual = salario_mensual * 12;
RUN;
```
En este caso, se crea un nuevo conjunto de datos `empleados_modificados`, donde se añade una nueva variable `sueldo_anual`, calculada a partir de `salario_mensual`.

## Explicación
Al trabajar con el comando SET, es importante tener en cuenta ciertos aspectos:

- **Orden de los datos**: El orden en que se leen los registros puede afectar los resultados, especialmente al usar operaciones que dependen del orden, como la acumulación de totales.
- **Manejo de variables no existentes**: Si se intenta acceder a una variable que no existe en el conjunto de datos leído, SAS generará un mensaje de advertencia, y la variable se creará con un valor de missing.
- **Duplicación de nombres de variables**: Si dos conjuntos de datos tienen variables con el mismo nombre, SAS mantendrá la variable del último conjunto leído, lo que puede producir resultados inesperados.

## Resumen en una línea
El comando SET en SAS permite leer y manipular conjuntos de datos existentes, facilitando la creación de nuevos registros y la combinación de datos.
<!--
Meta Description: # DATA en SAS: Comando Fundamental para la Manipulación de Datos ## Sinopsis El comando `DATA` en SAS es una instrucción esencial utilizada para crear...
Meta Keywords: datos, data, sas, para, variables
-->

# DATA en SAS: Comando Fundamental para la Manipulación de Datos

## Sinopsis
El comando `DATA` en SAS es una instrucción esencial utilizada para crear y manipular conjuntos de datos. Permite la entrada de datos, la transformación y la creación de nuevas variables, siendo fundamental en el flujo de trabajo de análisis de datos en SAS.

## Documentación
### Propósito
El propósito del comando `DATA` es iniciar un paso de datos en el que se pueden definir, modificar y gestionar conjuntos de datos. A través de este comando, los analistas pueden realizar operaciones como la creación de nuevas variables, la lectura de información desde fuentes externas y la aplicación de condiciones para filtrar o transformar datos.

### Uso
La sintaxis básica del comando `DATA` es la siguiente:

```sas
DATA nombre_del_dataset;
    /* Instrucciones para manipulación de datos */
RUN;
```

- `nombre_del_dataset`: Es el nombre del conjunto de datos que se desea crear o modificar.
- Las instrucciones pueden incluir la asignación de variables, la lectura de datos desde archivos o la aplicación de transformaciones.

### Detalles
- **Entrada de datos**: Se puede utilizar la instrucción `INPUT` para definir las variables y sus tipos.
- **Transformación de datos**: Se pueden realizar cálculos y crear nuevas variables utilizando expresiones aritméticas.
- **Condiciones**: Se pueden aplicar declaraciones `IF-THEN` para crear lógica condicional en la manipulación de datos.

## Ejemplos
### Ejemplo 1: Creación de un Conjunto de Datos Simple
```sas
DATA empleados;
    INPUT nombre $ salario;
    DATALINES;
    Juan 30000
    Ana 40000
    Pedro 35000
    ;
RUN;
```
Este ejemplo crea un conjunto de datos llamado `empleados` con nombres y salarios.

### Ejemplo 2: Creación de una Nueva Variable
```sas
DATA ventas;
    INPUT producto $ precio;
    margen = precio * 0.2; /* Cálculo del margen */
    DATALINES;
    ProductoA 100
    ProductoB 150
    ;
RUN;
```
En este caso, se añade una nueva variable `margen` que representa el 20% del precio.

## Explicación
Al utilizar el comando `DATA`, es importante tener en cuenta que:

- **Orden de las instrucciones**: El orden de las instrucciones es crítico. Las variables deben ser definidas antes de intentar utilizarlas.
- **Nombres de variables**: Los nombres de las variables deben seguir las reglas de nomenclatura de SAS, que incluyen no comenzar con un número y no utilizar espacios.
- **Tipos de datos**: Es fundamental especificar correctamente los tipos de datos (numéricos o caracteres) para evitar errores en el procesamiento.

## Resumen en una Línea
El comando `DATA` en SAS es crucial para crear y manipular conjuntos de datos, permitiendo a los usuarios realizar transformaciones y análisis efectivos en sus datos.
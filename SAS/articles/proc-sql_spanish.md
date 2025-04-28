<!--
Meta Description: # PROC SQL en SAS: Consulta y Manipulación de Datos Eficiente ## Sinopsis PROC SQL es una potente herramienta dentro del lenguaje de programación SAS ...
Meta Keywords: sql, proc, datos, sas, que
-->

# PROC SQL en SAS: Consulta y Manipulación de Datos Eficiente

## Sinopsis
PROC SQL es una potente herramienta dentro del lenguaje de programación SAS que permite realizar operaciones de consulta y manipulación de datos utilizando una sintaxis similar a SQL. A través de este procedimiento, los usuarios pueden combinar, filtrar y resumir datos de manera efectiva, facilitando la toma de decisiones basada en análisis de datos.

## Documentación
PROC SQL se utiliza para ejecutar sentencias SQL en SAS, lo que permite a los usuarios interactuar con conjuntos de datos de manera intuitiva. Su propósito principal es ofrecer una forma flexible de realizar operaciones complejas de consulta, permitiendo la integración de varias tablas y la ejecución de funciones agregadas.

### Uso
El procedimiento se inicia con la palabra clave `PROC SQL;` y se cierra con `QUIT;`. Dentro de este bloque, se pueden utilizar diversas sentencias SQL como `SELECT`, `FROM`, `WHERE`, `JOIN`, y `GROUP BY`, entre otras.

#### Sintaxis básica
```sas
PROC SQL;
   SELECT column1, column2
   FROM dataset
   WHERE condition;
QUIT;
```

### Detalles
- **SELECT**: Especifica las columnas que se desean recuperar.
- **FROM**: Indica la tabla o conjunto de datos desde el cual se extraen los datos.
- **WHERE**: Permite filtrar los resultados basándose en condiciones específicas.
- **JOIN**: Facilita la combinación de datos de múltiples tablas.
- **GROUP BY**: Agrupa los resultados para aplicar funciones agregadas.

PROC SQL también permite la creación de tablas temporales y vistas, así como la inclusión de funciones de agregado como `SUM`, `AVG`, `COUNT`, entre otras.

## Ejemplos
### Ejemplo 1: Consulta simple
```sas
PROC SQL;
   SELECT nombre, edad
   FROM empleados
   WHERE edad > 30;
QUIT;
```

### Ejemplo 2: Uso de funciones agregadas
```sas
PROC SQL;
   SELECT departamento, COUNT(*) AS total_empleados
   FROM empleados
   GROUP BY departamento;
QUIT;
```

### Ejemplo 3: Combinar tablas
```sas
PROC SQL;
   SELECT a.nombre, b.proyecto
   FROM empleados AS a
   JOIN proyectos AS b ON a.id_empleado = b.id_empleado;
QUIT;
```

## Explicación
Al utilizar PROC SQL, es importante tener en cuenta algunas consideraciones:

- **Sensibilidad a mayúsculas y minúsculas**: Los nombres de columnas y tablas son sensibles a las mayúsculas y minúsculas, lo que puede causar errores si no se utilizan correctamente.
- **Rendimiento**: Aunque PROC SQL es muy flexible, para conjuntos de datos extremadamente grandes, puede ser menos eficiente que otros procedimientos de SAS como DATA STEP.
- **Errores comunes**: Uno de los errores más comunes es no cerrar adecuadamente el bloque PROC SQL con `QUIT;`, lo que puede resultar en comportamientos inesperados en el código.

## Resumen en una línea
PROC SQL es una herramienta en SAS que permite realizar consultas y manipulaciones de datos de manera eficiente utilizando sintaxis SQL.
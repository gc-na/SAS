<!--
Meta Description: # ELSE en SAS: Control de Flujo en Programación SAS ## Sinopsis El comando `ELSE` en SAS es una parte esencial de la estructura de control de flujo qu...
Meta Keywords: else, que, sas, condición, uso
-->

# ELSE en SAS: Control de Flujo en Programación SAS

## Sinopsis
El comando `ELSE` en SAS es una parte esencial de la estructura de control de flujo que permite ejecutar diferentes bloques de código según si una condición específica es verdadera o falsa.

## Documentación
El `ELSE` en SAS se utiliza en conjunción con la instrucción `IF` para gestionar la lógica condicional en los programas. Su propósito principal es permitir que el programador especifique un bloque de código alternativo que se ejecutará cuando la condición del `IF` no se cumpla. Esto es fundamental para el desarrollo de programas que requieren decisiones basadas en los valores de datos.

### Uso
La sintaxis básica del uso de `ELSE` es la siguiente:

```sas
IF condición THEN acción1;
ELSE acción2;
```

Donde:
- **condición**: Es una expresión que se evalúa como verdadera o falsa.
- **acción1**: Es el bloque de código que se ejecutará si la condición es verdadera.
- **acción2**: Es el bloque de código que se ejecutará si la condición es falsa.

El uso de `ELSE` puede extenderse con múltiples condiciones utilizando `ELSE IF`, lo que permite evaluar múltiples expresiones de manera secuencial.

### Ejemplo
A continuación se presentan ejemplos simples del uso de `ELSE` en SAS:

**Ejemplo 1: Uso básico de ELSE**

```sas
data ejemplo;
    input edad;
    if edad >= 18 then estado = 'Adulto';
    else estado = 'Menor';
    datalines;
17
21
15
19
;
run;

proc print data=ejemplo;
run;
```

En este ejemplo, el programa clasifica a los individuos como 'Adulto' o 'Menor' según su edad.

**Ejemplo 2: Uso de ELSE IF**

```sas
data ejemplo2;
    input puntuacion;
    if puntuacion >= 90 then grado = 'A';
    else if puntuacion >= 80 then grado = 'B';
    else if puntuacion >= 70 then grado = 'C';
    else grado = 'D';
    datalines;
95
82
76
65
;
run;

proc print data=ejemplo2;
run;
```

Aquí, se evalúan múltiples condiciones para asignar un grado según la puntuación obtenida.

## Explicación
Al utilizar `ELSE`, es importante tener en cuenta algunas consideraciones y errores comunes:

- **Orden de evaluación**: La condición en el `IF` se evalúa primero. Si no se cumple, el bloque de `ELSE` se ejecuta. Esto significa que es crucial ordenar las condiciones correctamente para obtener los resultados deseados.
  
- **Falta de condiciones**: Si se omite `ELSE`, y la condición del `IF` es falsa, no se ejecutará ninguna acción, lo que puede llevar a resultados inesperados.

- **Uso con múltiples condiciones**: Al utilizar `ELSE IF`, asegúrate de que las condiciones sean mutuamente exclusivas para evitar confusiones en la evaluación.

- **Tipografía**: Recuerda que SAS es sensible a las mayúsculas y minúsculas en nombres de variables, lo que puede causar errores si no se mantiene consistencia.

## Resumen en una línea
El comando `ELSE` en SAS permite ejecutar bloques de código alternativos según el resultado de una condición evaluada con `IF`.
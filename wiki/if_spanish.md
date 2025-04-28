<!--
Meta Description: # IF en SAS: Condicionales en Programación ## Sinopsis El comando IF en SAS se utiliza para ejecutar condicionalmente instrucciones en función de si u...
Meta Keywords: else, sas, datos, instrucción, una
-->

# IF en SAS: Condicionales en Programación

## Sinopsis
El comando IF en SAS se utiliza para ejecutar condicionalmente instrucciones en función de si una expresión lógica es verdadera o falsa. Es fundamental en la toma de decisiones dentro de los programas SAS, permitiendo el manejo de datos y el control del flujo de ejecución.

## Documentación
El comando IF en SAS es una estructura de control que permite evaluar condiciones y ejecutar diferentes bloques de código según el resultado de esas evaluaciones. La sintaxis básica de una instrucción IF es:

```sas
IF condición THEN acción;
```

### Propósito
El propósito principal de la instrucción IF es permitir que el programa tome decisiones basadas en los valores de las variables. Esto es especialmente útil en la manipulación de datos y la creación de informes.

### Uso
La instrucción IF puede ser usada en varios contextos dentro de un programa SAS, incluyendo:
- **Data Step**: Para crear o modificar variables en un conjunto de datos.
- **Procedimientos**: Para filtrar o clasificar datos.

### Detalles
- **Condiciones complejas**: Se pueden combinar múltiples condiciones usando operadores lógicos como AND y OR.
- **Instrucción ELSE**: Se puede incluir una instrucción ELSE para proporcionar un bloque de código alternativo si la condición inicial no se cumple.
- **Múltiples condiciones**: Se pueden usar múltiples instrucciones IF-ELSE IF para evaluar diferentes condiciones en secuencia.

## Ejemplos
### Ejemplo básico
```sas
data ejemplo;
    set datos;
    if edad >= 18 then estado = 'Adulto';
    else estado = 'Menor';
run;
```

### Ejemplo con ELSE
```sas
data ejemplo;
    set datos;
    if ingreso > 50000 then categoria = 'Alto';
    else if ingreso > 30000 then categoria = 'Medio';
    else categoria = 'Bajo';
run;
```

### Ejemplo con condiciones múltiples
```sas
data ejemplo;
    set datos;
    if (sexo = 'Femenino' and edad < 30) then grupo = 'Joven Mujer';
    else if (sexo = 'Masculino' and edad < 30) then grupo = 'Joven Hombre';
    else grupo = 'Adulto';
run;
```

## Explicación
Al usar la instrucción IF, es importante considerar:
- **Orden de evaluación**: Las condiciones se evalúan en el orden en que aparecen. Si una condición es verdadera, las siguientes no se evaluarán.
- **Tipo de datos**: Asegúrate de que las comparaciones se realicen entre tipos de datos compatibles para evitar errores.
- **Falta de ELSE**: Si no se incluye una instrucción ELSE, las observaciones que no cumplan la condición inicial no recibirán ninguna acción, lo que puede resultar en valores no definidos.

## Resumen en una línea
La instrucción IF en SAS permite ejecutar acciones condicionalmente, facilitando la toma de decisiones en la programación y el análisis de datos.
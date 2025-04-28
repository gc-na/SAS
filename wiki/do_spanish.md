<!--
Meta Description: # DO en SAS: Comprendiendo la Estructura de Control de Flujo ## Sinopsis El comando "DO" en SAS es una estructura de control de flujo que permite ejec...
Meta Keywords: que, sas, ejemplo, una, bloque
-->

# DO en SAS: Comprendiendo la Estructura de Control de Flujo

## Sinopsis
El comando "DO" en SAS es una estructura de control de flujo que permite ejecutar un bloque de código varias veces, facilitando la iteración y la manipulación de datos dentro de un programa SAS.

## Documentación
### Propósito
El comando "DO" se utiliza en SAS para crear bucles iterativos, lo que permite ejecutar una serie de instrucciones repetidamente. Es esencial para realizar tareas como cálculos repetidos, generación de series de datos y manipulación de matrices.

### Uso
La sintaxis básica del comando "DO" es la siguiente:

```sas
DO <índice> = <valor_inicial> TO <valor_final>;
   <instrucciones>;
END;
```

- **índice**: La variable que se utiliza como contador del bucle.
- **valor_inicial**: El valor desde el cual comienza el contador.
- **valor_final**: El valor hasta el cual se ejecutará el bucle.
- **instrucciones**: El bloque de código que se ejecutará en cada iteración.

### Detalles
El comando "DO" puede utilizarse en varios contextos, incluyendo:
- **DO simple**: Para ejecutar un bloque de código un número específico de veces.
- **DO WHILE**: Para ejecutar un bloque de código mientras se cumpla una condición.
- **DO UNTIL**: Para ejecutar un bloque de código hasta que se cumpla una condición.

## Ejemplos
### Ejemplo 1: DO simple
```sas
DATA ejemplo;
   DO i = 1 TO 5;
      salida = i * 2;
      OUTPUT;
   END;
RUN;
```
Este ejemplo genera cinco registros donde la variable `salida` contiene el doble del índice `i`.

### Ejemplo 2: DO WHILE
```sas
DATA ejemplo;
   i = 1;
   DO WHILE (i <= 5);
      salida = i * 2;
      OUTPUT;
      i + 1;
   END;
RUN;
```
En este caso, se utiliza un bucle que continúa mientras `i` sea menor o igual a 5.

### Ejemplo 3: DO UNTIL
```sas
DATA ejemplo;
   i = 1;
   DO UNTIL (i > 5);
      salida = i * 2;
      OUTPUT;
      i + 1;
   END;
RUN;
```
Este ejemplo genera el mismo resultado que el anterior, pero el bucle se detiene una vez que `i` es mayor que 5.

## Explicación
### Errores Comunes
- **Olvidar el `END;`**: Es necesario cerrar el bloque de DO con `END;`, de lo contrario, SAS generará un error de sintaxis.
- **Condiciones incorrectas**: Usar condiciones que nunca se cumplen puede llevar a bucles infinitos, especialmente en los bucles DO WHILE y DO UNTIL.
- **Alcance de variables**: Asegúrate de que las variables utilizadas dentro del bucle están correctamente inicializadas y son accesibles en el contexto donde se utilizan.

### Notas Adicionales
- Los bucles "DO" son útiles para manipular grandes conjuntos de datos, pero se debe tener cuidado con el uso excesivo, ya que puede afectar el rendimiento del programa.

## Resumen en una línea
El comando "DO" en SAS permite la ejecución repetitiva de bloques de código, facilitando la manipulación de datos y la programación estructurada.
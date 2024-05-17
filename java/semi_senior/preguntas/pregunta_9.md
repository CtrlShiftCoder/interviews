# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior


## Pregunta 9
**¿Qué es la programación funcional en Java y cuáles son sus características principales?**

**Respuesta:**
La programación funcional en Java es un estilo de programación que trata las funciones como ciudadanos de primera clase. Sus características principales incluyen el uso de funciones de orden superior, inmutabilidad y la evitación de efectos secundarios.

**Ejemplo:**
```java
import java.util.Arrays;

public class FuncionalDemo {
    public static void main(String[] args) {
        // Uso de funciones de orden superior (map y reduce)
        int[] numeros = {1, 2, 3, 4, 5};
        int suma = Arrays.stream(numeros)
                         .map(x -> x * x)
                         .reduce(0, Integer::sum);
        System.out.println("Suma de cuadrados: " + suma);
    }
}


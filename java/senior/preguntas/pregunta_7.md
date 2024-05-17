# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 7
**¿Qué es la programación funcional y cómo se implementa en Java? Proporciona un ejemplo.**

**Respuesta:**
La programación funcional es un paradigma de programación que trata a las funciones como ciudadanos de primera clase y se centra en la aplicación de funciones y la evitación de estado mutable. En Java, se implementa utilizando interfaces funcionales y expresiones lambda. Ejemplos de funciones de orden superior incluyen `map`, `filter` y `reduce`.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<String> nombres = Arrays.asList("Ana", "Juan", "Pedro", "Maria");

        // Ejemplo de uso de programación funcional para filtrar nombres que comienzan con "A" y convertirlos a mayúsculas
        List<String> nombresFiltrados = nombres.stream()
                                               .filter(nombre -> nombre.startsWith("A"))
                                               .map(String::toUpperCase)
                                               .collect(Collectors.toList());

        System.out.println(nombresFiltrados); // Imprime "[ANA]"
    }
}
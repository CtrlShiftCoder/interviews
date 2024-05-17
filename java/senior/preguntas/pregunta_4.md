# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior


## Pregunta 4
**¿Qué son los `Streams` en Java y cuáles son sus características principales? Proporciona un ejemplo.**

**Respuesta:**
Los `Streams` en Java proporcionan una forma funcional de procesar colecciones de datos. Permiten operaciones como map, filter y reduce, y son especialmente útiles para manipular grandes conjuntos de datos de manera eficiente. Las características principales incluyen ser secuenciales o paralelos, operaciones intermedias y terminales, y lazy evaluation.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<String> nombres = Arrays.asList("Ana", "Juan", "Pedro", "Maria");

        // Ejemplo de uso de Streams para filtrar nombres que comienzan con "A" y convertirlos a mayúsculas
        nombres.stream()
               .filter(nombre -> nombre.startsWith("A"))
               .map(String::toUpperCase)
               .forEach(System.out::println);
    }
}
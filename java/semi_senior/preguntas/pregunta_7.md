# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 7
**¿Qué son los streams en Java y cuál es su propósito?**

**Respuesta:**
Los streams en Java son secuencias de datos que pueden ser procesadas de manera secuencial o paralela. Su propósito es proporcionar una manera más simple y concisa de trabajar con secuencias de elementos, como colecciones, arreglos o archivos.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;

public class StreamsDemo {
    public static void main(String[] args) {
        List<String> frutas = Arrays.asList("Manzana", "Banana", "Naranja");

        // Filtrar y mostrar solo las frutas que comienzan con 'M'
        frutas.stream()
            .filter(fruta -> fruta.startsWith("M"))
            .forEach(System.out::println);
    }
}
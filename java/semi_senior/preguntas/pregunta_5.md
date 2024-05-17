# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 5
**¿Qué son los genéricos en Java y cuál es su propósito?**

**Respuesta:**
Los genéricos en Java permiten crear clases y métodos que pueden trabajar con cualquier tipo de objeto. Su propósito es proporcionar una manera de crear código flexible y reutilizable que pueda manejar diferentes tipos de datos de manera segura durante la compilación.

**Ejemplo:**
```java
import java.util.*;

public class GenericosDemo {
    public static void main(String[] args) {
        // Crear una lista de strings
        List<String> lista = new ArrayList<>();
        lista.add("Hola");
        lista.add("Mundo");

        // Iterar sobre la lista y mostrar elementos
        for (String elemento : lista) {
            System.out.println(elemento);
        }
    }
}
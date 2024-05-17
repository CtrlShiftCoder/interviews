# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 7
**¿Qué es un `ArrayList` en Java?**

**Respuesta:**
`ArrayList` es una clase de la colección de Java que proporciona una implementación redimensionable de la interfaz `List`. Permite almacenar y acceder a elementos de forma dinámica.

**Ejemplo:**
```java
import java.util.ArrayList;

public class EjemploArrayList {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        lista.add("Manzana");
        lista.add("Banana");
        System.out.println(lista.get(0)); // Imprime "Manzana"
    }
}

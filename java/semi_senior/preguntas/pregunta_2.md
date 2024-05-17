# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 2
**¿Qué son las colecciones en Java y por qué son útiles?**

**Respuesta:**
Las colecciones en Java son estructuras de datos que permiten almacenar y manipular grupos de objetos. Son útiles porque proporcionan implementaciones eficientes de diversas estructuras de datos, como listas, conjuntos y mapas, facilitando la manipulación y gestión de datos en aplicaciones Java.

**Ejemplo:**
```java
import java.util.*;

public class ColeccionesDemo {
    public static void main(String[] args) {
        // Crear una lista de strings
        List<String> lista = new ArrayList<>();
        lista.add("Manzana");
        lista.add("Banana");
        lista.add("Naranja");

        // Iterar sobre la lista
        for (String fruta : lista) {
            System.out.println(fruta);
        }
    }
}
s
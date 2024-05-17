# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 3
**¿Cuál es la diferencia entre las clases `ArrayList` y `LinkedList` en Java y cuándo se debe usar cada una? Proporciona un ejemplo.**

**Respuesta:**
`ArrayList` y `LinkedList` son implementaciones diferentes de la interfaz `List` en Java. La diferencia principal radica en cómo se almacenan los elementos: `ArrayList` utiliza un arreglo dinámico, mientras que `LinkedList` utiliza una lista doblemente enlazada. Se debe usar `ArrayList` cuando se accede frecuentemente a elementos por índice y `LinkedList` cuando se realizan operaciones frecuentes de inserción y eliminación en el medio de la lista.

**Ejemplo:**
```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        // Ejemplo de uso de ArrayList
        List<String> arrayList = new ArrayList<>();
        arrayList.add("Uno");
        arrayList.add("Dos");
        arrayList.add("Tres");
        System.out.println("ArrayList: " + arrayList);

        // Ejemplo de uso de LinkedList
        List<String> linkedList = new LinkedList<>();
        linkedList.add("Uno");
        linkedList.add("Dos");
        linkedList.add("Tres");
        System.out.println("LinkedList: " + linkedList);
    }
}
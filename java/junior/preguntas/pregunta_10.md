# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 10
**¿Qué es un `HashMap` en Java?**

**Respuesta:**
`HashMap` es una estructura de datos que permite almacenar pares clave-valor y permite la búsqueda rápida de valores basados en la clave. Utiliza un hash para indexar las claves.

**Ejemplo:**
```java
import java.util.HashMap;

public class EjemploHashMap {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();
        map.put("Uno", 1);
        map.put("Dos", 2);
        System.out.println(map.get("Uno")); // Imprime "1"
    }
}


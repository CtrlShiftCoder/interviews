# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 6
**¿Qué es la reflexión en Java y cuáles son sus usos comunes? Proporcione un ejemplo.**

**Respuesta:**
La reflexión en Java es una característica que permite inspeccionar y manipular clases, métodos y campos en tiempo de ejecución. Se usa comúnmente en frameworks, depuración y pruebas para acceder y modificar propiedades privadas.

**Ejemplo:**
```java
import java.lang.reflect.Field;

class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
}

public class Main {
    public static void main(String[] args) throws Exception {
        Persona persona = new Persona("Juan", 30);

        // Ejemplo de uso de reflexión para acceder a un campo privado
        Field field = persona.getClass().getDeclaredField("nombre");
        field.setAccessible(true);
        String nombre = (String) field.get(persona);
        System.out.println("Nombre: " + nombre); // Imprime "Juan"
    }
}
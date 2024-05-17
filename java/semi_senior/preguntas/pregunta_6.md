# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 6
**¿Qué es la reflexión en Java y para qué se utiliza?**

**Respuesta:**
La reflexión en Java es una capacidad que permite a un programa examinar o modificar su propia estructura, comportamiento y metadatos en tiempo de ejecución. Se utiliza para crear aplicaciones flexibles, frameworks y herramientas que necesitan examinar o modificar el comportamiento de los objetos en tiempo de ejecución.

**Ejemplo:**
```java
import java.lang.reflect.*;

public class ReflexionDemo {
    public static void main(String[] args) throws Exception {
        // Obtener la clase de una instancia
        Persona persona = new Persona("Juan", 25);
        Class<?> clasePersona = persona.getClass();

        // Obtener métodos de la clase
        Method[] metodos = clasePersona.getMethods();
        for (Method metodo : metodos) {
            System.out.println(metodo.getName());
        }
    }
}

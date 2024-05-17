# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 2
**Explica el concepto de inmutabilidad en Java y por qué es importante en la programación concurrente. Proporciona un ejemplo.**

**Respuesta:**
La inmutabilidad en Java se refiere a la incapacidad de cambiar el estado de un objeto una vez creado. Es importante en programación concurrente porque evita condiciones de carrera y problemas de concurrencia al garantizar que los objetos compartidos no sean modificados por múltiples hilos al mismo tiempo.

**Ejemplo:**
```java
public class Persona {
    private final String nombre;
    private final int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public String getNombre() {
        return nombre;
    }

    public int getEdad() {
        return edad;
    }
}

public class Main {
    public static void main(String[] args) {
        Persona persona = new Persona("Juan", 30);
        // Los valores de nombre y edad no pueden ser modificados después de la creación del objeto
        // Esto asegura que el objeto sea inmutable
    }
}

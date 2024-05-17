# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 4
**¿Qué es un constructor en Java?**

**Respuesta:**
Un constructor es un método especial que se utiliza para inicializar objetos. Tiene el mismo nombre que la clase y no tiene tipo de retorno.

**Ejemplo:**
```java
public class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
}
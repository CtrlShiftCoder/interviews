# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

### Pregunta 1
**¿Qué es una clase en Java?**

**Respuesta:**
Una clase en Java es una plantilla o un blueprint a partir del cual se crean los objetos. Una clase define los atributos y comportamientos que los objetos creados a partir de la clase pueden tener.

**Ejemplo:**
```java
public class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    // Getters y setters
    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public int getEdad() {
        return edad;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }
}

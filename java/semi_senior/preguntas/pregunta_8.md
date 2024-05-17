# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 8
**¿Qué es la anotación `@Override` en Java y cuál es su uso?**

**Respuesta:**
La anotación `@Override` en Java se utiliza para indicar que un método en una subclase está sobrescribiendo un método en la superclase. Es una buena práctica utilizar esta anotación para evitar errores de compilación al sobrescribir métodos.

**Ejemplo:**
```java
public class Animal {
    public void hacerSonido() {
        System.out.println("Sonido de animal");
    }
}

public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Ladrido");
    }
}

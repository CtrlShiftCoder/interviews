# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 5
**¿Qué es la herencia en Java?**

**Respuesta:**
La herencia en Java es un mecanismo que permite a una clase derivada (subclase) heredar campos y métodos de una clase base (superclase). Facilita la reutilización del código.

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
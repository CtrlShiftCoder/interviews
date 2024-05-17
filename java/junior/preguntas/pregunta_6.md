# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 6
**¿Qué es una interfaz en Java?**

**Respuesta:**
Una interfaz en Java es un contrato que una clase puede implementar. Define métodos que la clase debe proporcionar, pero no incluye la implementación de esos métodos.

**Ejemplo:**
```java
public interface Volador {
    void volar();
}

public class Pajaro implements Volador {
    @Override
    public void volar() {
        System.out.println("El pájaro vuela");
    }
}
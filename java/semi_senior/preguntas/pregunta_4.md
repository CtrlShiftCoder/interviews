# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 4
**¿Qué es el manejo de excepciones en Java y por qué es importante?**

**Respuesta:**
El manejo de excepciones en Java es el proceso de detectar y manejar situaciones excepcionales durante la ejecución del programa. Es importante porque permite al programa responder de manera controlada a condiciones excepcionales, evitando que el programa se bloquee o se comporte de manera inesperada.

**Ejemplo:**
```java
public class ExcepcionesDemo {
    public static void main(String[] args) {
        try {
            int resultado = 10 / 0; // Genera una excepción de división por cero
        } catch (ArithmeticException e) {
            System.out.println("No se puede dividir por cero.");
        }
    }
}
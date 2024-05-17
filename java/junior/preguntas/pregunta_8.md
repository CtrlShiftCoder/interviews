# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 8
**¿Qué es una excepción en Java?**

**Respuesta:**
Una excepción en Java es un evento que ocurre durante la ejecución de un programa y que interrumpe el flujo normal de las instrucciones. Las excepciones pueden ser manejadas usando bloques `try`, `catch` y `finally`.

**Ejemplo:**
```java
public class EjemploExcepcion {
    public static void main(String[] args) {
        try {
            int resultado = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("No se puede dividir por cero.");
        } finally {
            System.out.println("Bloque finally ejecutado.");
        }
    }


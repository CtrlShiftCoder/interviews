# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

## Pregunta 2
**¿Qué es una variable local en Java?**

**Respuesta:**
Una variable local es una variable que se declara dentro de un método, constructor o bloque. Solo es accesible dentro de ese método, constructor o bloque específico.

**Ejemplo:**
```java
public void miMetodo() {
    int numero = 10; // variable local
    System.out.println(numero);
}
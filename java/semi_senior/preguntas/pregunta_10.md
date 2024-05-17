# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 10
**¿Qué es la anotación `@FunctionalInterface` en Java y cuál es su propósito?**

**Respuesta:**
La anotación `@FunctionalInterface` en Java se utiliza para indicar que una interfaz es una interfaz funcional. Su propósito es proporcionar una verificación en tiempo de compilación de que la interfaz tiene exactamente un método abstracto, lo que la hace elegible para ser utilizada con expresiones lambda y referencias de métodos.

**Ejemplo:**
```java
@FunctionalInterface
interface OperacionMatematica {
    int operar(int a, int b);
}

public class FuncionalInterfaceDemo {
    public static void main(String[] args) {
        OperacionMatematica suma = (a, b) -> a + b;
        System.out.println("Suma: " + suma.operar(5, 3));
    }
}
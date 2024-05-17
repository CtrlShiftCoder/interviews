# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 5
**Explique el principio de diseño SOLID y cómo se aplica en Java. Proporcione un ejemplo.**

**Respuesta:**
SOLID es un acrónimo que representa cinco principios de diseño de software: Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation y Dependency Inversion. En Java, estos principios se aplican utilizando técnicas como la creación de clases y métodos con una única responsabilidad, la programación orientada a interfaces, y la inyección de dependencias.

**Ejemplo:**

Principio de Responsabilidad Única (Single Responsibility Principle - SRP):
```java
// Clase con múltiples responsabilidades
class Impresora {
    public void imprimirDocumento(Documento documento) {
        // Lógica para imprimir el documento
    }

    public void escanearDocumento(Documento documento) {
        // Lógica para escanear el documento
    }
}

// Clases separadas con responsabilidades únicas
class Impresora {
    public void imprimirDocumento(Documento documento) {
        // Lógica para imprimir el documento
    }
}

class Escaner {
    public void escanearDocumento(Documento documento) {
        // Lógica para escanear el documento
    }
}

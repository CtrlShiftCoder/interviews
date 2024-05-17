# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 1
**¿Qué es la serialización en Java y cuál es su propósito?**

**Respuesta:**
La serialización en Java es el proceso de convertir un objeto en una secuencia de bytes para que pueda ser almacenado en memoria, en un archivo o transmitido a través de la red. Su propósito es permitir la persistencia de objetos y la comunicación entre aplicaciones distribuidas.

**Ejemplo:**
```java
import java.io.*;

public class SerializacionDemo {
    public static void main(String[] args) {
        try {
            // Objeto a serializar
            Persona persona = new Persona("Juan", 25);

            // Serialización
            FileOutputStream archivoSalida = new FileOutputStream("persona.ser");
            ObjectOutputStream out = new ObjectOutputStream(archivoSalida);
            out.writeObject(persona);
            out.close();
            archivoSalida.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

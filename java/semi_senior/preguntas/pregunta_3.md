# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Pregunta 3
**¿Qué es la concurrencia en Java y cómo se puede lograr?**

**Respuesta:**
La concurrencia en Java se refiere a la capacidad de un programa para realizar múltiples tareas simultáneamente. Se puede lograr mediante el uso de hilos (threads) y la sincronización de acceso a recursos compartidos.

**Ejemplo:**
```java
public class ConcurrenciaDemo {
    public static void main(String[] args) {
        // Crear e iniciar un hilo
        Thread thread = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Hilo en ejecución: " + i);
                try {
                    Thread.sleep(1000); // Dormir el hilo por 1 segundo
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });
        thread.start(); // Iniciar el hilo
    }
}

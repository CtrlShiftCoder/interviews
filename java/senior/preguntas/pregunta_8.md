# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 8
**Explique el concepto de concurrencia y paralelismo en Java. Proporcione un ejemplo de cómo se pueden lograr en aplicaciones Java.**

**Respuesta:**
La concurrencia se refiere a la capacidad de un programa para manejar múltiples tareas simultáneamente, mientras que el paralelismo implica la ejecución simultánea real de múltiples tareas. En Java, la concurrencia se logra utilizando hilos (`Thread`) y la ejecución paralela se logra utilizando `ExecutorService` y `ForkJoinPool`.

**Ejemplo de concurrencia:**
```java
public class ConcurrenciaEjemplo {
    public static void main(String[] args) {
        Thread hilo1 = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Hilo 1: " + i);
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        Thread hilo2 = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Hilo 2: " + i);
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        hilo1.start();
        hilo2.start();
    }
}

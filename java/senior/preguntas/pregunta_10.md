# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 10
**Explica cómo se maneja la concurrencia en Java utilizando los conceptos de bloqueo, sincronización y monitorización. Proporcione un ejemplo de cómo se pueden utilizar estos conceptos en la práctica.**

**Respuesta:**
En Java, la concurrencia se maneja utilizando bloqueos (`synchronized`), que evitan que varios hilos accedan simultáneamente a un recurso compartido. La sincronización se logra al asegurar que solo un hilo pueda ejecutar ciertas partes del código a la vez. Los monitores se utilizan para garantizar que solo un hilo pueda ejecutar un bloque de código a la vez.

**Ejemplo:**
Supongamos que tenemos una clase `Contador` que incrementa un valor compartido. Podemos utilizar bloqueos, sincronización y monitorización para garantizar que las operaciones de incremento sean seguras en entornos concurrentes:

```java
public class Contador {
    private int valor = 0;

    public synchronized void incrementar() {
        valor++;
    }

    public int obtenerValor() {
        return valor;
    }
}

public class Main {
    public static void main(String[] args) {
        Contador contador = new Contador();

        // Crear hilos que incrementen el contador simultáneamente
        Thread hilo1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        Thread hilo2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        // Iniciar los hilos
        hilo1.start();
        hilo2.start();

        // Esperar a que los hilos terminen
        try {
            hilo1.join();
            hilo2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        // Imprimir el valor final del contador
        System.out.println("Valor final del contador: " + contador.obtenerValor());
    }
}

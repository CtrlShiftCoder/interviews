# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

## Pregunta 1
**¿Qué son los `CompletableFuture` en Java y cómo se utilizan para la programación asíncrona?**

**Respuesta:**
`CompletableFuture` es una clase en Java que se utiliza para representar un valor futuro que puede completarse de manera asincrónica. Es parte del paquete `java.util.concurrent` y se usa para realizar tareas asincrónicas sin bloqueo.

**Ejemplo:**
```java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.ExecutionException;

public class CompletableFutureDemo {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        CompletableFuture<String> future = CompletableFuture.supplyAsync(() -> {
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            return "Hola Mundo";
        });

        // Realiza otras tareas...

        System.out.println(future.get()); // Espera y obtiene el resultado
    }
}
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


## Pregunta 2
**Explica el concepto de inmutabilidad en Java y por qué es importante en la programación concurrente. Proporciona un ejemplo.**

**Respuesta:**
La inmutabilidad en Java se refiere a la incapacidad de cambiar el estado de un objeto una vez creado. Es importante en programación concurrente porque evita condiciones de carrera y problemas de concurrencia al garantizar que los objetos compartidos no sean modificados por múltiples hilos al mismo tiempo.

**Ejemplo:**
```java
public class Persona {
    private final String nombre;
    private final int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public String getNombre() {
        return nombre;
    }

    public int getEdad() {
        return edad;
    }
}

public class Main {
    public static void main(String[] args) {
        Persona persona = new Persona("Juan", 30);
        // Los valores de nombre y edad no pueden ser modificados después de la creación del objeto
        // Esto asegura que el objeto sea inmutable
    }
}


## Pregunta 3
**¿Cuál es la diferencia entre las clases `ArrayList` y `LinkedList` en Java y cuándo se debe usar cada una? Proporciona un ejemplo.**

**Respuesta:**
`ArrayList` y `LinkedList` son implementaciones diferentes de la interfaz `List` en Java. La diferencia principal radica en cómo se almacenan los elementos: `ArrayList` utiliza un arreglo dinámico, mientras que `LinkedList` utiliza una lista doblemente enlazada. Se debe usar `ArrayList` cuando se accede frecuentemente a elementos por índice y `LinkedList` cuando se realizan operaciones frecuentes de inserción y eliminación en el medio de la lista.

**Ejemplo:**
```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        // Ejemplo de uso de ArrayList
        List<String> arrayList = new ArrayList<>();
        arrayList.add("Uno");
        arrayList.add("Dos");
        arrayList.add("Tres");
        System.out.println("ArrayList: " + arrayList);

        // Ejemplo de uso de LinkedList
        List<String> linkedList = new LinkedList<>();
        linkedList.add("Uno");
        linkedList.add("Dos");
        linkedList.add("Tres");
        System.out.println("LinkedList: " + linkedList);
    }
}

## Pregunta 4
**¿Qué son los `Streams` en Java y cuáles son sus características principales? Proporciona un ejemplo.**

**Respuesta:**
Los `Streams` en Java proporcionan una forma funcional de procesar colecciones de datos. Permiten operaciones como map, filter y reduce, y son especialmente útiles para manipular grandes conjuntos de datos de manera eficiente. Las características principales incluyen ser secuenciales o paralelos, operaciones intermedias y terminales, y lazy evaluation.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<String> nombres = Arrays.asList("Ana", "Juan", "Pedro", "Maria");

        // Ejemplo de uso de Streams para filtrar nombres que comienzan con "A" y convertirlos a mayúsculas
        nombres.stream()
               .filter(nombre -> nombre.startsWith("A"))
               .map(String::toUpperCase)
               .forEach(System.out::println);
    }
}

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

## Pregunta 6
**¿Qué es la reflexión en Java y cuáles son sus usos comunes? Proporcione un ejemplo.**

**Respuesta:**
La reflexión en Java es una característica que permite inspeccionar y manipular clases, métodos y campos en tiempo de ejecución. Se usa comúnmente en frameworks, depuración y pruebas para acceder y modificar propiedades privadas.

**Ejemplo:**
```java
import java.lang.reflect.Field;

class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
}

public class Main {
    public static void main(String[] args) throws Exception {
        Persona persona = new Persona("Juan", 30);

        // Ejemplo de uso de reflexión para acceder a un campo privado
        Field field = persona.getClass().getDeclaredField("nombre");
        field.setAccessible(true);
        String nombre = (String) field.get(persona);
        System.out.println("Nombre: " + nombre); // Imprime "Juan"
    }
}


## Pregunta 7
**¿Qué es la programación funcional y cómo se implementa en Java? Proporciona un ejemplo.**

**Respuesta:**
La programación funcional es un paradigma de programación que trata a las funciones como ciudadanos de primera clase y se centra en la aplicación de funciones y la evitación de estado mutable. En Java, se implementa utilizando interfaces funcionales y expresiones lambda. Ejemplos de funciones de orden superior incluyen `map`, `filter` y `reduce`.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<String> nombres = Arrays.asList("Ana", "Juan", "Pedro", "Maria");

        // Ejemplo de uso de programación funcional para filtrar nombres que comienzan con "A" y convertirlos a mayúsculas
        List<String> nombresFiltrados = nombres.stream()
                                               .filter(nombre -> nombre.startsWith("A"))
                                               .map(String::toUpperCase)
                                               .collect(Collectors.toList());

        System.out.println(nombresFiltrados); // Imprime "[ANA]"
    }
}

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

## Pregunta 9
**¿Qué es la inyección de dependencias y por qué es importante en el desarrollo de software? Proporcione un ejemplo de cómo se implementa en Java utilizando frameworks como Spring.**

**Respuesta:**
La inyección de dependencias es un patrón de diseño en el que las dependencias de un objeto se proporcionan desde el exterior en lugar de ser creadas internamente. Es importante porque facilita la modularidad, la reutilización y la prueba de unidades independientes. En Java, se implementa comúnmente utilizando frameworks como Spring, donde las dependencias se definen en archivos de configuración o mediante anotaciones.

**Ejemplo con Spring:**
Supongamos que tenemos una clase `Cliente` que depende de una interfaz `Servicio`. Utilizando Spring, podemos configurar la inyección de dependencias de la siguiente manera:

```java
public interface Servicio {
    void realizarAccion();
}

public class ServicioImpl implements Servicio {
    @Override
    public void realizarAccion() {
        System.out.println("Realizando acción...");
    }
}

public class Cliente {
    private Servicio servicio;

    public Cliente(Servicio servicio) {
        this.servicio = servicio;
    }

    public void ejecutar() {
        servicio.realizarAccion();
    }
}

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

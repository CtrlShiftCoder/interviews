# Preguntas para el Perfil Semi-Senior en Java

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


## Pregunta 2
**¿Qué son las colecciones en Java y por qué son útiles?**

**Respuesta:**
Las colecciones en Java son estructuras de datos que permiten almacenar y manipular grupos de objetos. Son útiles porque proporcionan implementaciones eficientes de diversas estructuras de datos, como listas, conjuntos y mapas, facilitando la manipulación y gestión de datos en aplicaciones Java.

**Ejemplo:**
```java
import java.util.*;

public class ColeccionesDemo {
    public static void main(String[] args) {
        // Crear una lista de strings
        List<String> lista = new ArrayList<>();
        lista.add("Manzana");
        lista.add("Banana");
        lista.add("Naranja");

        // Iterar sobre la lista
        for (String fruta : lista) {
            System.out.println(fruta);
        }
    }
}


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


## Pregunta 4
**¿Qué es el manejo de excepciones en Java y por qué es importante?**

**Respuesta:**
El manejo de excepciones en Java es el proceso de detectar y manejar situaciones excepcionales durante la ejecución del programa. Es importante porque permite al programa responder de manera controlada a condiciones excepcionales, evitando que el programa se bloquee o se comporte de manera inesperada.

**Ejemplo:**
```java
public class ExcepcionesDemo {
    public static void main(String[] args) {
        try {
            int resultado = 10 / 0; // Genera una excepción de división por cero
        } catch (ArithmeticException e) {
            System.out.println("No se puede dividir por cero.");
        }
    }
}


## Pregunta 5
**¿Qué son los genéricos en Java y cuál es su propósito?**

**Respuesta:**
Los genéricos en Java permiten crear clases y métodos que pueden trabajar con cualquier tipo de objeto. Su propósito es proporcionar una manera de crear código flexible y reutilizable que pueda manejar diferentes tipos de datos de manera segura durante la compilación.

**Ejemplo:**
```java
import java.util.*;

public class GenericosDemo {
    public static void main(String[] args) {
        // Crear una lista de strings
        List<String> lista = new ArrayList<>();
        lista.add("Hola");
        lista.add("Mundo");

        // Iterar sobre la lista y mostrar elementos
        for (String elemento : lista) {
            System.out.println(elemento);
        }
    }
}

## Pregunta 6
**¿Qué es la reflexión en Java y para qué se utiliza?**

**Respuesta:**
La reflexión en Java es una capacidad que permite a un programa examinar o modificar su propia estructura, comportamiento y metadatos en tiempo de ejecución. Se utiliza para crear aplicaciones flexibles, frameworks y herramientas que necesitan examinar o modificar el comportamiento de los objetos en tiempo de ejecución.

**Ejemplo:**
```java
import java.lang.reflect.*;

public class ReflexionDemo {
    public static void main(String[] args) throws Exception {
        // Obtener la clase de una instancia
        Persona persona = new Persona("Juan", 25);
        Class<?> clasePersona = persona.getClass();

        // Obtener métodos de la clase
        Method[] metodos = clasePersona.getMethods();
        for (Method metodo : metodos) {
            System.out.println(metodo.getName());
        }
    }
}


## Pregunta 7
**¿Qué son los streams en Java y cuál es su propósito?**

**Respuesta:**
Los streams en Java son secuencias de datos que pueden ser procesadas de manera secuencial o paralela. Su propósito es proporcionar una manera más simple y concisa de trabajar con secuencias de elementos, como colecciones, arreglos o archivos.

**Ejemplo:**
```java
import java.util.Arrays;
import java.util.List;

public class StreamsDemo {
    public static void main(String[] args) {
        List<String> frutas = Arrays.asList("Manzana", "Banana", "Naranja");

        // Filtrar y mostrar solo las frutas que comienzan con 'M'
        frutas.stream()
            .filter(fruta -> fruta.startsWith("M"))
            .forEach(System.out::println);
    }
}

## Pregunta 8
**¿Qué es la anotación `@Override` en Java y cuál es su uso?**

**Respuesta:**
La anotación `@Override` en Java se utiliza para indicar que un método en una subclase está sobrescribiendo un método en la superclase. Es una buena práctica utilizar esta anotación para evitar errores de compilación al sobrescribir métodos.

**Ejemplo:**
```java
public class Animal {
    public void hacerSonido() {
        System.out.println("Sonido de animal");
    }
}

public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Ladrido");
    }
}


## Pregunta 9
**¿Qué es la programación funcional en Java y cuáles son sus características principales?**

**Respuesta:**
La programación funcional en Java es un estilo de programación que trata las funciones como ciudadanos de primera clase. Sus características principales incluyen el uso de funciones de orden superior, inmutabilidad y la evitación de efectos secundarios.

**Ejemplo:**
```java
import java.util.Arrays;

public class FuncionalDemo {
    public static void main(String[] args) {
        // Uso de funciones de orden superior (map y reduce)
        int[] numeros = {1, 2, 3, 4, 5};
        int suma = Arrays.stream(numeros)
                         .map(x -> x * x)
                         .reduce(0, Integer::sum);
        System.out.println("Suma de cuadrados: " + suma);
    }
}



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


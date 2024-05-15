# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

### Pregunta 1
**¿Qué es una clase en Java?**

**Respuesta:**
Una clase en Java es una plantilla o un blueprint a partir del cual se crean los objetos. Una clase define los atributos y comportamientos que los objetos creados a partir de la clase pueden tener.

**Ejemplo:**
```java
public class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    // Getters y setters
    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public int getEdad() {
        return edad;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }
}

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


## Pregunta 3
**¿Qué es un método en Java?**

**Respuesta:**
Un método en Java es un bloque de código que realiza una tarea específica y se ejecuta cuando se le invoca. Puede tomar parámetros y retornar un valor.

**Ejemplo:**
```java
public int sumar(int a, int b) {
    return a + b;
}

## Pregunta 4
**¿Qué es un constructor en Java?**

**Respuesta:**
Un constructor es un método especial que se utiliza para inicializar objetos. Tiene el mismo nombre que la clase y no tiene tipo de retorno.

**Ejemplo:**
```java
public class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
}

## Pregunta 5
**¿Qué es la herencia en Java?**

**Respuesta:**
La herencia en Java es un mecanismo que permite a una clase derivada (subclase) heredar campos y métodos de una clase base (superclase). Facilita la reutilización del código.

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


## Pregunta 6
**¿Qué es una interfaz en Java?**

**Respuesta:**
Una interfaz en Java es un contrato que una clase puede implementar. Define métodos que la clase debe proporcionar, pero no incluye la implementación de esos métodos.

**Ejemplo:**
```java
public interface Volador {
    void volar();
}

public class Pajaro implements Volador {
    @Override
    public void volar() {
        System.out.println("El pájaro vuela");
    }
}



## Pregunta 7
**¿Qué es un `ArrayList` en Java?**

**Respuesta:**
`ArrayList` es una clase de la colección de Java que proporciona una implementación redimensionable de la interfaz `List`. Permite almacenar y acceder a elementos de forma dinámica.

**Ejemplo:**
```java
import java.util.ArrayList;

public class EjemploArrayList {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        lista.add("Manzana");
        lista.add("Banana");
        System.out.println(lista.get(0)); // Imprime "Manzana"
    }
}



## Pregunta 8
**¿Qué es una excepción en Java?**

**Respuesta:**
Una excepción en Java es un evento que ocurre durante la ejecución de un programa y que interrumpe el flujo normal de las instrucciones. Las excepciones pueden ser manejadas usando bloques `try`, `catch` y `finally`.

**Ejemplo:**
```java
public class EjemploExcepcion {
    public static void main(String[] args) {
        try {
            int resultado = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("No se puede dividir por cero.");
        } finally {
            System.out.println("Bloque finally ejecutado.");
        }
    }


## Pregunta 9
**¿Qué es el polimorfismo en Java?**

**Respuesta:**
El polimorfismo en Java es la capacidad de un objeto para tomar muchas formas. Permite que una referencia de superclase se refiera a un objeto de una subclase.

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

public class Gato extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Maullido");
    }
}

public class EjemploPolimorfismo {
    public static void main(String[] args) {
        Animal miAnimal = new Perro();
        miAnimal.hacerSonido(); // Imprime "Ladrido"

        miAnimal = new Gato();
        miAnimal.hacerSonido(); // Imprime "Maullido"
    }
}

## Pregunta 10
**¿Qué es un `HashMap` en Java?**

**Respuesta:**
`HashMap` es una estructura de datos que permite almacenar pares clave-valor y permite la búsqueda rápida de valores basados en la clave. Utiliza un hash para indexar las claves.

**Ejemplo:**
```java
import java.util.HashMap;

public class EjemploHashMap {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();
        map.put("Uno", 1);
        map.put("Dos", 2);
        System.out.println(map.get("Uno")); // Imprime "1"
    }
}


# Preguntas Técnicas para Java con Respuestas y Ejemplos

## Junior

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
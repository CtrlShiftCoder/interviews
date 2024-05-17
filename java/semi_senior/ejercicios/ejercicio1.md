# Pruebas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

## Ejercicio 1: Implementación de un Servicio de Biblioteca

### Instrucciones:
Implementa una clase `Biblioteca` que gestione una colección de libros. Cada libro debe tener un título, un autor y un año de publicación. La clase `Biblioteca` debe proporcionar métodos para:

1. Agregar un libro a la biblioteca.
2. Eliminar un libro de la biblioteca por su título.
3. Buscar un libro por su título.
4. Listar todos los libros ordenados por el año de publicación.

### Ejemplo:
```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

class Libro {
    private String titulo;
    private String autor;
    private int anoPublicacion;

    public Libro(String titulo, String autor, int anoPublicacion) {
        this.titulo = titulo;
        this.autor = autor;
        this.anoPublicacion = anoPublicacion;
    }

    public String getTitulo() {
        return titulo;
    }

    public String getAutor() {
        return autor;
    }

    public int getAnoPublicacion() {
        return anoPublicacion;
    }

    @Override
    public String toString() {
        return titulo + " - " + autor + " (" + anoPublicacion + ")";
    }
}

class Biblioteca {
    private List<Libro> libros;

    public Biblioteca() {
        this.libros = new ArrayList<>();
    }

    public void agregarLibro(Libro libro) {
        libros.add(libro);
    }

    public void eliminarLibro(String titulo) {
        libros.removeIf(libro -> libro.getTitulo().equalsIgnoreCase(titulo));
    }

    public Libro buscarLibro(String titulo) {
        for (Libro libro : libros) {
            if (libro.getTitulo().equalsIgnoreCase(titulo)) {
                return libro;
            }
        }
        return null;
    }

    public List<Libro> listarLibrosOrdenadosPorAno() {
        List<Libro> librosOrdenados = new ArrayList<>(libros);
        librosOrdenados.sort(Comparator.comparingInt(Libro::getAnoPublicacion));
        return librosOrdenados;
    }
}

public class BibliotecaDemo {
    public static void main(String[] args) {
        Biblioteca biblioteca = new Biblioteca();
        biblioteca.agregarLibro(new Libro("El Quijote", "Miguel de Cervantes", 1605));
        biblioteca.agregarLibro(new Libro("Cien Años de Soledad", "Gabriel García Márquez", 1967));
        biblioteca.agregarLibro(new Libro("Don Juan Tenorio", "José Zorrilla", 1844));

        System.out.println("Buscar libro 'Cien Años de Soledad':");
        System.out.println(biblioteca.buscarLibro("Cien Años de Soledad"));

        System.out.println("\nLista de libros ordenados por año de publicación:");
        for (Libro libro : biblioteca.listarLibrosOrdenadosPorAno()) {
            System.out.println(libro);
        }

        biblioteca.eliminarLibro("Don Juan Tenorio");
        System.out.println("\nLista de libros después de eliminar 'Don Juan Tenorio':");
        for (Libro libro : biblioteca.listarLibrosOrdenadosPorAno()) {
            System.out.println(libro);
        }
    }
}

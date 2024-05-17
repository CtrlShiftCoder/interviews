# Preguntas Técnicas para Java con Respuestas y Ejemplos

##  Senior

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
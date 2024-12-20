# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 10  
**¿Qué es Lazy Loading en Angular y cómo se implementa?**

**Respuesta:**  
El **Lazy Loading** es una técnica utilizada en Angular para cargar módulos de manera diferida, es decir, solo cuando son requeridos por el usuario. Esto ayuda a mejorar el rendimiento de la aplicación, ya que los módulos no se cargan de forma inmediata, sino que se cargan de manera perezosa (lazy) cuando el usuario navega hacia una ruta que necesita ese módulo.

**Ejemplo de implementación de Lazy Loading:**

1. **Definir un módulo para Lazy Loading:**

Primero, se debe crear un módulo que se cargará de forma perezosa. Por ejemplo, supongamos que tenemos un módulo llamado `AdminModule` que solo se debe cargar cuando el usuario accede a una ruta relacionada con el administrador.

```bash
ng generate module admin --route admin --module app.module

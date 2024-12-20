# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 9  
**¿Qué es el `NgRx` y cómo se utiliza para manejar el estado de la aplicación en Angular?**

**Respuesta:**  
`NgRx` es una librería para Angular basada en el patrón de diseño Redux, que ayuda a gestionar el estado de la aplicación de manera reactiva. Utiliza `Observables` para manejar cambios de estado y asegura que la aplicación sea predecible y fácil de mantener. `NgRx` se compone de acciones, reductores, efectos y el store, que en conjunto permiten gestionar el flujo de datos de manera centralizada en la aplicación.

**Ejemplo:**

1. **Configuración básica de `NgRx`:**

Primero, instalamos las dependencias necesarias para trabajar con `NgRx`:

```bash
npm install @ngrx/store @ngrx/effects

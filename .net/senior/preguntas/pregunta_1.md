# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 1  
**¿Qué es el cambio de detección (Change Detection) en Angular y cómo funciona?**

**Respuesta:**  
El cambio de detección en Angular es el proceso mediante el cual Angular verifica si los datos vinculados a la vista han cambiado. Si detecta un cambio, actualiza la vista en consecuencia. Angular utiliza un mecanismo de detección basado en la **zona** (zone.js) que realiza comprobaciones de manera eficiente en cada ciclo de eventos.

**Ejemplo:**
- En un componente, Angular detecta cambios cuando se actualiza una variable de estado vinculada a la vista.

```typescript
// src/app/app.component.ts
export class AppComponent {
  count = 0;

  increment() {
    this.count++;
  }
}

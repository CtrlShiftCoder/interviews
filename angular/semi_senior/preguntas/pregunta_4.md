# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 4  
**¿Qué es el `ChangeDetectionStrategy` en Angular y cuál es la diferencia entre `Default` y `OnPush`?**

**Respuesta:**  
`ChangeDetectionStrategy` en Angular es un mecanismo que determina cómo y cuándo se actualiza la vista de un componente. Angular realiza la detección de cambios para reflejar los cambios de datos en la vista. Existen dos estrategias principales: `Default` y `OnPush`.

- **`Default`:** Angular realiza la detección de cambios de manera regular. Esto significa que siempre que algo en el componente o en sus dependencias cambie, Angular actualizará la vista.
- **`OnPush`:** Con esta estrategia, Angular solo revisa el componente cuando:
  1. Cambia uno de sus inputs.
  2. Se dispara un evento (como un clic).
  3. Se llama manualmente a `markForCheck()` para forzar una revisión.

Usar `OnPush` puede mejorar el rendimiento de la aplicación al reducir las comprobaciones innecesarias.

**Ejemplo:**  

1. **Uso de `ChangeDetectionStrategy.Default`:**
```typescript
import { Component, ChangeDetectionStrategy } from '@angular/core';

@Component({
  selector: 'app-componente-default',
  template: `<p>{{ mensaje }}</p>`,
  changeDetection: ChangeDetectionStrategy.Default, // Estrategia por defecto
})
export class ComponenteDefaultComponent {
  mensaje = 'Hola, mundo!';
}

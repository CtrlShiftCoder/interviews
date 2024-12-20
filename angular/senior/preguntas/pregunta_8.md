# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 8  
**¿Qué es el Two-way Data Binding en Angular y cómo se utiliza?**

**Respuesta:**  
El **Two-way Data Binding** en Angular permite que los cambios en el modelo de datos se reflejen automáticamente en la vista y viceversa, sin necesidad de que el desarrollador tenga que escribir código adicional para gestionar la sincronización entre ambos. Esto facilita la interacción y actualización dinámica de los datos en la aplicación.

En Angular, el two-way data binding se implementa utilizando la directiva `ngModel`.

**Ejemplo de uso de Two-way Data Binding:**

1. **Componente con Two-way Binding:**

```typescript
// src/app/app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
})
export class AppComponent {
  name: string = '';
}

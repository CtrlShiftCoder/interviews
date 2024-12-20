# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 8  
**¿Qué es el two-way data binding en Angular y cómo se implementa?**  

**Respuesta:**  
El two-way data binding (enlace bidireccional de datos) es una característica de Angular que permite sincronizar el modelo de datos y la vista. Esto significa que cualquier cambio en la vista se refleja automáticamente en el modelo, y viceversa.

**Ejemplo:**  

1. **Uso de `[(ngModel)]` para implementar el two-way data binding:**  
```typescript
// componente.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-formulario',
  template: `
    <input [(ngModel)]="nombre" placeholder="Escribe tu nombre" />
    <p>Hola, {{ nombre }}!</p>
  `,
})
export class FormularioComponent {
  nombre: string = '';
}

# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 3  
**¿Qué es el binding de datos en Angular y cuáles son sus tipos?**  

**Respuesta:**  
El binding de datos (o data binding) en Angular es el mecanismo que permite sincronizar datos entre el modelo (clase del componente) y la vista (HTML). Hay tres tipos principales de binding en Angular:

1. **Interpolación (`{{ }}`):** Para mostrar valores desde el componente en el HTML.  
2. **Binding de propiedades (`[property]`):** Para asignar valores del componente a propiedades de un elemento HTML.  
3. **Binding de eventos (`(event)`):** Para ejecutar lógica en el componente cuando ocurren eventos en la vista.  
4. **Binding bidireccional (`[(ngModel)]`):** Para sincronizar datos en ambas direcciones (entre el modelo y la vista).

**Ejemplo:**  
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-binding-ejemplo',
  template: `
    <h1>{{ titulo }}</h1> <!-- Interpolación -->
    <input [value]="titulo" (input)="actualizarTitulo($event)" /> <!-- Binding de propiedad y evento -->
    <p>Binding bidireccional:</p>
    <input [(ngModel)]="titulo" /> <!-- Binding bidireccional -->
  `,
})
export class BindingEjemploComponent {
  titulo: string = 'Hola, Angular';

  actualizarTitulo(event: Event): void {
    const input = event.target as HTMLInputElement;
    this.titulo = input.value;
  }
}

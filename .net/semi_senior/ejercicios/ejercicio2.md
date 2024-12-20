## Semi Senior

### Ejercicio 3
**Crea un componente en Angular que reciba una lista de elementos y los filtre según un término de búsqueda.**

**Respuesta:**

1. Crea el componente usando Angular CLI:

```bash
ng generate component filtro

2. Modifica el componente para implementar el filtro:
filtro.component.ts:

import { Component } from '@angular/core';

@Component({
  selector: 'app-filtro',
  templateUrl: './filtro.component.html',
  styleUrls: ['./filtro.component.css']
})

export class FiltroComponent {
  elementos: string[] = ['Manzana', 'Banana', 'Cereza', 'Durazno', 'Uva'];
  terminoBusqueda: string = '';
  elementosFiltrados: string[] = this.elementos;

  filtrar() {
    this.elementosFiltrados = this.elementos.filter(item =>
      item.toLowerCase().includes(this.terminoBusqueda.toLowerCase())
    );
  }
}

filtro.component.html:

<input type="text" [(ngModel)]="terminoBusqueda" (input)="filtrar()" placeholder="Buscar...">
<ul>
  <li *ngFor="let item of elementosFiltrados">{{ item }}</li>
</ul>
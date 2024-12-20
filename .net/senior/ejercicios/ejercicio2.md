## Senior

### Ejercicio 5
**Implementa un sistema de paginación y filtrado para una lista de elementos en Angular, donde los datos provienen de un servicio simulado y la paginación se maneja tanto en el frontend como en el backend.**

**Respuesta:**

1. Primero, crea el servicio que simula la API de backend:

**`data.service.ts`**:
```typescript
import { Injectable } from '@angular/core';
import { Observable, of } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class DataService {

  private data: string[] = [
    'Manzana', 'Banana', 'Cereza', 'Durazno', 'Uva', 'Pera', 'Melón', 'Kiwi', 'Frambuesa', 'Arándano',
    'Naranja', 'Mango', 'Papaya', 'Coco', 'Granada', 'Aguacate', 'Fresa', 'Mango', 'Plátano', 'Peral'
  ];

  constructor() { }

  obtenerDatos(pagina: number, itemsPorPagina: number, filtro: string): Observable<string[]> {
    const start = (pagina - 1) * itemsPorPagina;
    const end = start + itemsPorPagina;
    const filtrados = this.data.filter(item => item.toLowerCase().includes(filtro.toLowerCase()));
    return of(filtrados.slice(start, end));
  }

  obtenerTotal(pagina: number, itemsPorPagina: number, filtro: string): Observable<number> {
    const filtrados = this.data.filter(item => item.toLowerCase().includes(filtro.toLowerCase()));
    return of(filtrados.length);
  }
}

# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 8  
**¿Qué es el `RxJS` y cómo se utiliza para manejar datos asincrónicos en Angular?**

**Respuesta:**  
`RxJS` (Reactive Extensions for JavaScript) es una librería para programación reactiva usando Observables. En Angular, `RxJS` se utiliza principalmente para manejar datos asincrónicos como respuestas HTTP, eventos del usuario, temporizadores, entre otros. Utiliza el patrón de diseño Observable para permitir que los componentes "se suscriban" a los datos y reaccionen cuando estos cambian o cuando se reciben nuevos datos.

**Ejemplo:**

1. **Instalación y uso básico de `RxJS`:**

En Angular, las operaciones asincrónicas como las solicitudes HTTP se realizan con `Observable` y se gestionan con operadores de `RxJS`. Un ejemplo común es obtener datos de una API con el servicio `HttpClient`.

```typescript
import { Component, OnInit } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Component({
  selector: 'app-usuario',
  template: `
    <h1>Usuarios</h1>
    <ul>
      <li *ngFor="let usuario of usuarios">{{ usuario.name }}</li>
    </ul>
  `,
})
export class UsuarioComponent implements OnInit {
  usuarios: any[] = [];

  constructor(private http: HttpClient) {}

  ngOnInit(): void {
    // Usando un Observable para hacer una solicitud HTTP
    this.getUsuarios().subscribe((data) => {
      this.usuarios = data; // Asignamos la respuesta a la variable 'usuarios'
    });
  }

  getUsuarios(): Observable<any[]> {
    return this.http.get<any[]>('https://jsonplaceholder.typicode.com/users'); // Retorna un Observable
  }
}

# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 5  
**¿Qué es un `Observable` en Angular y cómo se utiliza en un componente?**

**Respuesta:**  
Un `Observable` en Angular es una estructura de datos que permite trabajar con flujos de datos asíncronos. Es una parte fundamental de la programación reactiva en Angular y se utiliza para manejar datos que cambian con el tiempo, como las respuestas de solicitudes HTTP, eventos del usuario, temporizadores, etc. Los `Observables` emiten valores y permiten suscribirse a estos valores para recibir notificaciones cuando los datos cambian.

Un `Observable` es una representación de una colección de eventos que se pueden observar y manejar a medida que ocurren, permitiendo una gestión eficiente de la asincronía.

**Ejemplo:**  

1. **Uso de `Observable` para manejar una solicitud HTTP:**
```typescript
import { Component, OnInit } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Component({
  selector: 'app-usuario-lista',
  template: `
    <ul>
      <li *ngFor="let usuario of usuarios">{{ usuario.nombre }}</li>
    </ul>
  `,
})
export class UsuarioListaComponent implements OnInit {
  usuarios: any[] = [];

  constructor(private http: HttpClient) {}

  ngOnInit(): void {
    // Llamada HTTP que devuelve un Observable
    this.obtenerUsuarios().subscribe(
      (data) => {
        this.usuarios = data; // Asignar los datos a la variable usuarios
      },
      (error) => {
        console.error('Error al obtener los usuarios:', error);
      }
    );
  }

  obtenerUsuarios(): Observable<any[]> {
    return this.http.get<any[]>('https://api.example.com/usuarios');
  }
}

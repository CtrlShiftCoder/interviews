# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 2  
**¿Qué es un Observable en Angular y cómo se usa con HTTP?**

**Respuesta:**  
Un **Observable** es una secuencia de valores o eventos que pueden ser emitidos de forma asíncrona. En Angular, se utilizan principalmente para manejar flujos de datos asíncronos, como respuestas HTTP. Los **Observables** permiten suscribirse a flujos de datos y manejar los resultados cuando estén disponibles.

**Ejemplo de uso con HTTP:**

```typescript
// src/app/user.service.ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root',
})
export class UserService {
  constructor(private http: HttpClient) {}

  getUsers(): Observable<any[]> {
    return this.http.get<any[]>('https://api.example.com/users');
  }
}

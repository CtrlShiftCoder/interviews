# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 9  
**¿Qué es un Observable en Angular y cómo se utiliza con un servicio?**

**Respuesta:**  
Un **Observable** en Angular es un patrón de diseño que permite trabajar con flujos de datos asincrónicos. Un observable puede emitir valores de manera sincrónica o asincrónica, y los componentes pueden suscribirse a ellos para recibir estos valores. En Angular, los **Observables** son ampliamente utilizados en servicios para manejar operaciones asíncronas, como llamadas HTTP, temporizadores, eventos de usuario, entre otros.

**Ejemplo de uso de un Observable con un servicio HTTP:**

1. **Creación de un servicio que retorna un Observable:**

```typescript
// src/app/user.service.ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root',
})
export class UserService {
  private apiUrl = 'https://jsonplaceholder.typicode.com/users';

  constructor(private http: HttpClient) {}

  getUsers(): Observable<any[]> {
    return this.http.get<any[]>(this.apiUrl);
  }
}

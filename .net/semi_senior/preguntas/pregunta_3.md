# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 3  
**¿Qué es un `Service` en Angular y cómo se inyecta en un componente?**

**Respuesta:**  
Un `Service` en Angular es una clase que proporciona funcionalidades reutilizables y lógicas de negocio que pueden ser compartidas entre componentes. Los servicios son ideales para manejar tareas como la gestión de datos, llamadas a APIs, almacenamiento local, y más. Los servicios en Angular se inyectan en componentes o en otros servicios mediante el sistema de inyección de dependencias (DI) de Angular.

**Ejemplo:**  

1. **Creación de un Service:**
```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { Usuario } from './usuario.model';

@Injectable({
  providedIn: 'root', // Hace que el servicio sea accesible a nivel de toda la aplicación
})
export class UsuarioService {
  private apiUrl = 'https://api.example.com/usuarios';

  constructor(private http: HttpClient) {}

  // Método para obtener usuarios desde la API
  obtenerUsuarios(): Observable<Usuario[]> {
    return this.http.get<Usuario[]>(this.apiUrl);
  }

  // Método para obtener un usuario por ID
  obtenerUsuarioPorId(id: string): Observable<Usuario> {
    return this.http.get<Usuario>(`${this.apiUrl}/${id}`);
  }
}

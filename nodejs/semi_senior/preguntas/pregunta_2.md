# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 2  
**¿Qué es un `Interceptor` en Angular y cómo se utiliza?**

**Respuesta:**  
Un `Interceptor` en Angular es una herramienta poderosa para interceptar y modificar las solicitudes HTTP (peticiones) y las respuestas antes de que lleguen a la aplicación o al servidor. Esto se utiliza comúnmente para agregar encabezados a las solicitudes, manejar errores globalmente, agregar autenticación (token de autorización) o registrar las peticiones.

**Ejemplo:**  

1. **Creación de un Interceptor:**
```typescript
import { Injectable } from '@angular/core';
import { HttpEvent, HttpHandler, HttpInterceptor, HttpRequest } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
    // Obtener el token de autenticación (por ejemplo, desde localStorage)
    const authToken = localStorage.getItem('auth_token');

    // Clonar la solicitud y agregar el token al encabezado Authorization
    const authReq = req.clone({
      setHeaders: {
        Authorization: `Bearer ${authToken}`,
      },
    });

    // Enviar la solicitud modificada
    return next.handle(authReq);
  }
}

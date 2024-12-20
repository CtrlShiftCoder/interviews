# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 7  
**¿Qué es un `Service` en Angular y cómo se utiliza para compartir datos entre componentes?**

**Respuesta:**  
Un `Service` en Angular es una clase que se utiliza para encapsular la lógica de negocio, la manipulación de datos y la comunicación entre componentes. Los servicios proporcionan una forma de compartir funcionalidades y datos entre diferentes partes de la aplicación sin tener que duplicar código. Los `Services` se inyectan en los componentes mediante el mecanismo de inyección de dependencias de Angular.

**Ejemplo:**  

1. **Creación de un servicio:**

Primero, creamos un servicio que manejará los datos compartidos. El servicio puede tener métodos para obtener, agregar o modificar datos.

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root', // El servicio es proporcionado globalmente en la aplicación
})
export class DataService {
  private datos: string[] = ['dato1', 'dato2', 'dato3'];

  constructor() {}

  obtenerDatos(): string[] {
    return this.datos;
  }

  agregarDato(dato: string): void {
    this.datos.push(dato);
  }
}

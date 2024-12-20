# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 5  
**¿Qué es el enrutador (Router) en Angular y cómo funciona?**  

**Respuesta:**  
El enrutador en Angular (Router) es una herramienta que permite la navegación entre diferentes vistas o componentes dentro de una aplicación. Gestiona las rutas y permite cargar dinámicamente los componentes asociados según la URL.

**Ejemplo:**  

1. **Definición de rutas:**  
```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent }, // Ruta raíz
  { path: 'about', component: AboutComponent }, // Ruta /about
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}

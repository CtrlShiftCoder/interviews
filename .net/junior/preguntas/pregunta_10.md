# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 10  
**¿Qué es el routing en Angular y cómo se configura?**

**Respuesta:**  
El routing en Angular permite navegar entre diferentes vistas o páginas de una aplicación sin recargar la página completa. Utiliza una arquitectura basada en rutas, donde cada ruta está asociada a un componente específico.

**Ejemplo:**  

1. **Configuración de las rutas en el módulo de la aplicación:**  
```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent },  // Ruta para la página principal
  { path: 'about', component: AboutComponent },  // Ruta para la página 'about'
];

@NgModule({
  declarations: [AppComponent, HomeComponent, AboutComponent],
  imports: [BrowserModule, RouterModule.forRoot(routes)], // Importar y configurar las rutas
  bootstrap: [AppComponent],
})
export class AppModule {}

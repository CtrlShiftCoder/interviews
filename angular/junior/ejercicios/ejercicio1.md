# Pruebas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Ejercicio 1
**Escribe un componente en Angular que reciba un nombre como entrada y lo muestre en una etiqueta `<h1>`**

**Respuesta:**

1. Primero, crea el componente usando Angular CLI:

```bash
ng generate component saludo

2. Luego, edita los archivos generados:

import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-saludo',
  templateUrl: './saludo.component.html',
  styleUrls: ['./saludo.component.css']
})
export class SaludoComponent {
  @Input() nombre: string = '';
}

saludo.component.html:
<h1>¡Hola, {{ nombre }}!</h1>


app.component.html (o el archivo donde desees usar el componente):
<app-saludo [nombre]="'Juan'"></app-saludo>
# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 4  
**¿Qué es un Pipe en Angular y cómo se utiliza?**

**Respuesta:**  
Un **Pipe** en Angular es una función que se usa para transformar datos en una vista. Los pipes permiten modificar el formato de los datos sin alterar los datos originales. Pueden ser utilizados para formatear fechas, monedas, texto, entre otros.

**Ejemplo de uso de Pipe:**

1. **Pipe integrado:**

Angular proporciona varios pipes integrados, como `date`, `currency`, y `uppercase`. Aquí se usa el pipe `date` para mostrar una fecha en un formato específico.

```html
<!-- src/app/app.component.html -->
<p>{{ currentDate | date:'short' }}</p>

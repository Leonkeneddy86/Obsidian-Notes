
## CSS (Cascading Style Sheets) es un lenguaje de estilo utilizado para describir la presentación de un documento HTML. Permite aplicar estilos a elementos HTML, como colores, fuentes, márgenes, espaciados, y mucho más. A continuación, te muestro algunos conceptos básicos y ejemplos de cómo usar CSS para darle estilo a una página web.

### Cómo incluir CSS en un documento HTML

Hay tres formas principales de incluir CSS en un documento HTML:

- **CSS en línea**: Se aplica directamente a un elemento HTML usando el atributo `style`.
`<h1 style="color: blue; font-size: 24px;">Título en Azul</h1>`

**CSS interno**: Se incluye dentro de una etiqueta `<style>` en la sección `<head>` del documento. 
(La forma correcta de usar CSS, es de forma externa y no meter estilos dentro del propio HTML)
`<head> 2 <style> 3 body { 4 background-color: #f0f0f0; 5 } 6 h1 { 7 color: green; 8 } 9 </style> 10</head>`

**CSS externo**: Se enlaza a un archivo CSS externo usando la etiqueta `<link>` en la sección `<head>`

`<head> 2 <link rel="stylesheet" href="styles.css"> 3</head>`

### Selectores CSS

Los selectores son patrones que se utilizan para seleccionar los elementos HTML que deseas estilizar. Algunos selectores comunes son:

- **Selector de tipo**: Selecciona todos los elementos de un tipo específico.

	`p { 2 color: red; /* Aplica color rojo a todos los párrafos */ 3}`

	- **Selector de clase**: Selecciona todos los elementos que tienen una clase específica. Se define con un punto (`.`).
    
    `.mi-clase { 2    font-size: 20px; /* Aplica un tamaño de fuente de 20px a los elementos con la clase "mi-clase" */ 3}`
    
- **Selector de ID**: Selecciona un elemento específico que tiene un ID. Se define con un símbolo de almohadilla (`#`).
    
    `#mi-id { 2    background-color: yellow; /* Aplica un fondo amarillo al elemento con el ID "mi-id" */ 3}`
    
- **Selector de atributo**: Selecciona elementos basados en un atributo específico
    
    `a[target="_blank"] { 2    color: blue; /* Aplica color azul a todos los enlaces que se abren en una nueva pestaña */ 3}`
    

### 3. Propiedades CSS comunes

Aquí hay algunas propiedades CSS comunes que puedes usar para estilizar tu página:

- **Color y fondo**:
    
    `body { 2    background-color: #f0f0f0; /* Color de fondo */ 3    color: #333; /* Color del texto */ 4}`
    
- **Fuentes**:
    
    `1h1 { 2    font-family: 'Arial', sans-serif; /* Tipo de fuente */ 3    font-size: 24px; /* Tamaño de fuente */ 4    font-weight: bold; /* Grosor de la fuente */ 5}`
    
- **Márgenes y rellenos**:
    
    `1p { 2    margin: 20px; /* Espacio exterior */ 3    padding: 10px; /* Espacio interior */ 4}`
    
- **Bordes**:
    
    `1div { 2    border: 1px solid black; /* Borde de 1px, sólido y negro */ 3    border-radius: 5px; /* Bordes redondeados */ 4}`
    
- **Tamaño y posición**:
    
    `1img { 2    width: 100%; /* Ancho del 100% del contenedor */ 3    height: auto; /* Altura automática para mantener la proporción */ 4}`
    

### 4. Ejemplo completo

Aquí tienes un ejemplo completo de cómo se puede usar CSS para estilizar una página web:


`1<!DOCTYPE html> 2<html lang="es"> 3<head> 4    <meta charset="UTF-8"> 5    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 6    <title>Ejemplo de CSS</title> 7    <link rel="stylesheet" href="styles.css"> 8    <style> 9        body { 10            background-color: #f0f0f0; 11            color: #333; 12            font-family: Arial, sans-serif; 13        } 14        h1 { 15            color: green; 16            text-align: center; 17        } 18        p { 19            margin: 20px; 20            padding: 10px; 21            border: 1px solid #ccc; 22            border-radius: 5px; 23        } 24        .mi-clase { 25`


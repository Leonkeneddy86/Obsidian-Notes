## La estructura básica de una página web en HTML se compone de varios elementos que definen su contenido y su presentación. A continuación, te muestro la estructura básica de un documento HTML, junto con algunas propiedades y elementos comunes que puedes utilizar.

![[Estructura HTML.png]]

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título de la Página</title>
    <link rel="stylesheet" href="styles.css"> <!-- Enlace a un archivo CSS externo -->
    <script src="script.js" defer></script> <!-- Enlace a un archivo JavaScript externo -->
</head>
<body>
    <header>
        <h1>Encabezado Principal</h1>
        <nav>
            <ul>
                <li><a href="#seccion1">Sección 1</a></li>
                <li><a href="#seccion2">Sección 2</a></li>
                <li><a href="#seccion3">Sección 3</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="seccion1">
            <h2>Sección 1</h2>
            <p>Contenido de la sección 1.</p>
        </section>

        <section id="seccion2">
            <h2>Sección 2</h2>
            <p>Contenido de la sección 2.</p>
        </section>

        <section id="seccion3">
            <h2>Sección 3</h2>
            <p>Contenido de la sección 3.</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Tu Nombre. Todos los derechos reservados.</p>
    </footer>
</body>
</html>

### Descripción de la estructura

1. **`<!DOCTYPE html>`**: Declara el tipo de documento y la versión de HTML que se está utilizando (HTML5 en este caso).
    
2. **`<html lang="es">`**: Elemento raíz del documento HTML. El atributo `lang` especifica el idioma del contenido (en este caso, español).
    
3. **`<head>`**: Contiene metadatos sobre el documento, como el título, enlaces a hojas de estilo y scripts.
    
    - **`<meta charset="UTF-8">`**: Define la codificación de caracteres utilizada (UTF-8 es la más común).
    - **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**: Hace que la página sea responsiva en dispositivos móviles.
    - **`<title>`**: Título de la página que aparece en la pestaña del navegador.
    - **`<link>`**: Enlace a un archivo CSS externo para estilos.
    - **`<script>`**: Enlace a un archivo JavaScript externo.
4. **`<body>`**: Contiene el contenido visible de la página.
    
    - **`<header>`**: Sección de encabezado que generalmente incluye el título y la navegación.
    - **`<nav>`**: Elemento de navegación que contiene enlaces a diferentes secciones de la página.
    - **`<main>`**: Contiene el contenido principal de la página.
    - **`<section>`**: Secciones del contenido, cada una con un encabezado y párrafos.
    - **`<footer>`**: Sección de pie de página que generalmente incluye información de derechos de autor y enlaces adicionales.

### Propiedades y elementos comunes

- **Encabezados**: `<h1>`, `<h2>`, `<h3>`, etc., para definir títulos y subtítulos.
- **Párrafos**: `<p>` para texto.
- **Listas**: `<ul>` (lista desordenada) y `<ol>` (lista ordenada) para crear listas.
- **Enlaces**: `<a href="URL">Texto del enlace</a>` para crear hipervínculos.
- **Imágenes**: `<img src="ruta/a/la/imagen.jpg" alt="Descripción de la imagen">` para insertar imágenes.
- **Tablas**: `<table>`, `<tr>`, `<td>`, etc., para crear tablas.

#  FlexBox y Grid

![[22-CSS-Flexbox-y-Grid.pdf]]


# Accesibilidad


![[Accesibilidad WEB.pdf]]
## Como ver responsive en móvil?
-  PowerShell (modo Administrador)
-  `ipconfig`  
- copias la IP de tu PC 
-  Luego, en proyecto:  
- `php artisan serve --host= Aqui la IP --port=8000`
- La dirección que genera, te la envías por WhatsApp y puedes abrirla en el móvil
# Extensiones Para HTML, CSS, JAVASCRIPT

- **Live Server (Ritwick Dey)** Link: (https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- **ESLint (Microsoft)** Link: (https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- **HTML/CSS/JavaScript Snippets (Eno Yao)** Link: (https://marketplace.visualstudio.com/items?itemName=Wscats.html-snippets)
- **Prettier - Code formatter (Prettier)** Link: (https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

	# Libros de HTML

	![[Libro HTML Academia X.pdf]]
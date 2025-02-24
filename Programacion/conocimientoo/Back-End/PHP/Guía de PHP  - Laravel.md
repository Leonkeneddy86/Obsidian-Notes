 guía para crear un proyecto en Laravel. He organizado la información en secciones claras y he añadido algunos comentarios para facilitar la comprensión.

---

Aquí tienes el texto refactorizado sobre la creación de un proyecto en Laravel, manteniendo toda la información original:

---



### 1. Crear Nuevo Proyecto
```bash
composer create-project --prefer-dist laravel/laravel NombreDeTuCarpeta
```

### 2. Gestión de Dependencias
```bash
# Node.js
npm install && npm run dev

# Composer
composer install
composer update
```

### 3. Servidor y Configuración
```bash
php artisan serve
php artisan key:generate
php artisan config:cache
```

---

## 🗄 Estructura de Base de Datos

### Migraciones y Modelos
```bash
# Crear migración con modelo y controlador
php artisan make:model NombreModelo -mcr

# Ejecutar migraciones
php artisan migrate:fresh --seed
```

### Factories y Seeders
```bash
php artisan make:factory NombreFactory
php artisan make:seeder NombreSeeder
```

---

## 🧪 Testing Avanzado

### Configuración Xdebug

### Verificar Si Xdebug esta instalado

```
`php -v`
```


### Renombrar el archivo en:

```
C:\xampp\php\ext\php_xdebug.dll
```


```
# php.ini
[xdebug] zend_extension = xdebug xdebug.remote_autostart = 1 xdebug.profiler_append = 0 xdebug.profiler_enable = 0 xdebug.profiler_enable_trigger = 0 xdebug.profiler_output_dir = "c:\xampp\tmp"; xdebug.profiler_output_name = "cachegrind.out.%t-%s" xdebug.remote_enable = 1 xdebug.remote_handler = "dbgp" xdebug.remote_host = "127.0.0.1" xdebug.remote_log="c:\xampp\tmp\xdebug.txt" xdebug.remote_port = 9000 xdebug.trace_output_dir = "c:\xampp\tmp"; xdebug.remote_cookie_expire_time = 36000 xdebug.mode=coverage xdebug.start_with_request=yes

```

### Generar Reportes
```bash
# Reporte básico
php artisan test --coverage

# Reporte HTML
php artisan test --coverage-html=coverage-report

# Type Coverage con Pest
./vendor/bin/pest --type-coverage --min=70
```


### Midiendo Test Coverage con Pest 

```
En primer lugar, tenemos que instalar Pest y su extensión para el type coverage:  composer require pestphp/pest --dev --with-all-dependencies

./vendor/bin/pest --init

Para instalar el plugin: composer require pestphp/pest-plugin-type-coverage --dev
```

---

## 🔐 Autenticación y API

### Scaffolding de Auth
```bash
composer require laravel/ui
php artisan ui bootstrap --auth
```

### Configuración JWT
- [Generador JWT](https://www.javainuse.com/jwtgenerator)
- [Documentación Oficial](https://jwt.io/)

### Controladores API
```bash
php artisan make:controller Api/NombreControlador --resource
```

---

## 🚨 Solución de Errores Comunes

### Error MySQL en XAMPP
1. Renombrar carpeta `data` → `dataold`
2. Crear nueva carpeta `data` vacía
3. Copiar contenido de `backup` → `data`
4. Mover `ibdata1` desde `dataold`
5. **Excluir**: mysql, performance_schema y phpmyadmin

[[XAMPP MySQL Error Solution|Ver procedimiento completo]]  https://www.youtube.com/watch?v=5cCT1ThLqqU&ab_channel=CodigoInformatico

---

## 🖥 Frontend con Blade

### Estructura Básica
```
resources/views/
├── layouts/
│   └── app.blade.php
└── components/
    ├── header.blade.php
    └── footer.blade.php
```

### Estilos CSS
```bash
public/css/app.css
```

---

## 🔌 Extensiones Recomendadas

### Para Laravel
- [[Laravel Blade Snippets]]
- [[Laravel Intellisense]]
- [[Blade Formatter]]

### Para PHP
- [[PHP Intelephense]]
- [[PHP Namespace Resolver]]
- [[PHP CS Fixer]]

---

## 🔄 Flujo de Trabajo MVC

```bash
# Crear elemento MVC completo
php artisan make:model Nombre -mcr
```

---

## 📚 Recursos Adicionales
- [[Test Coverage en Laravel]]
- [[Relaciones entre Tablas|Diagrama de relaciones]]
- [[Faker Data Generator|Repositorio Faker PHP]]
``` 

### Formatos Obsidian:
- Usa `[[ ]]` para enlaces internos entre notas
- Las imágenes se referencian con `![[nombre-archivo.png]]`
- Los archivos PDF se vinculan como `[[NombreArchivo.pdf]]`
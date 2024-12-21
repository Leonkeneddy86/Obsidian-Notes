## Crear Proyecto en Laravel

###### Copia y pega esta línea de código en tu proyecto de V

`composer create-project --prefer-dist laravel/laravel NombreDeTuCarpeta`

# Iniciar siempre servidor Nodejs

- `npm install`
- `npm update` (en caso de hacer un fork del repositorio, o actualizar npm)
- `npm run dev` Iniciar servidor PHP/Laravel

# Instalación de composer en tu proyecto

- `composer install`
- (instala composer en el proyecto)
- `composer update` 
- (en caso de tener que actualizar)
# Iniciar servidor PHP Laravel

```
	npm run build
	composer run dev
```
```
- php artisan serve
```

# Generar key para archivo .env
- `php artisan install key:generate`` 
- (fijarse en el archivo `.env` para comprobar que se haya generado)
- `php artisan config:cache` 
- (para resetear la KEY)
# Generar test y Reporte en el Index
```
- php artisan test --coverage
- php artisan test --coverage-html=coverage-report
```



![[Test_coverage_para_Laravel.pdf]]


# Error de Xampp

![[Error_de_Xampp.pdf]]

# Hacer Migraciones de tu código a la base de datos y crear una tabla, o dos.

```
php artisan migrate:fresh 
php artisan migrate:fresh --seed
php artisan make:migration create_NombreDeTuTabla_table
```

# La instalación de la API luego la podremos comprobar con Postman

###### - Comando instalar API (CarpetaRoutes)

- `php artisan install:api`

	###### En app/http/controllers, creamos la carpeta api y mediante el siguiente comando creamos la API
	
	`php artisan make:controller Api/NombreDeTuControlador --resource`
	
	###### Esto también se tiene que repetir si hacemos tablas relacionadas 
	
    En `phpunit.xml` se descomentan las líneas.

## Comando para hacer modelo, controlador y tabla (Esto es para hacer tablas relacionadas)


![[Relaciones entre tablas.png]]

- `php artisan make:model Follow -mcr`

## Empezar a trabajar con Blade

##### - En views crea la carpeta components y layouts; dentro de layout crea archivo app.blade.php
##### - En components crea footer.blade.php y header.blade.php y rellena con basicos
##### -  En public crea carpeta css y dentro el archivo app.css y le metes estilos básicos 
## Empezar a trabajar con el patrón de diseño MVC


![[Patron de diseño MVC.png]]


###### - Para instalar el Modelo:  `php artisan make:model NombreDeTuModelo`
###### - Para instalar el controlador:  `php artisan make:controller NombreDeTuControlador`
###### - Para instalar la vista:  `php artisan make:view home`  

## ## Creación de test y correr los test desde la terminal

`php artisan make:test NombreTest`

  `php artisan test --env=testing`

	php artisan test

		php artisan test --coverage


# Creación de Factorias

`php artisan make:factory NombreFactory`

## Crear Faker para PHP Vanilla o Laravel

 # GitHub (https://github.com/fzaninotto/Faker)
## Extensiones para Laravel

-  Laravel Blade Snippets (Winnie Lin)  Link: (https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-blade)
-  Laravel Extra Intellisense (amir)  Link: (https://marketplace.visualstudio.com/items?itemName=amiralizadeh9480.laravel-extra-intellisense)
-  Laravel Blade formatter (Shuhei Hayashibara)  Link: (https://marketplace.visualstudio.com/items?itemName=shufo.vscode-blade-formatter)
-  Laravel intellisense (Mohamed Benhida Link: (https://marketplace.visualstudio.com/items?itemName=mohamedbenhida.laravel-intellisense)
-  PHP Namespace Resolver - Mehedi Hassan Link: (https://marketplace.visualstudio.com/items?itemName=MehediDracula.php-namespace-resolver)
## Extensiones PHP Vanilla 

- PHP Intelephense (Ben Mewburn)  Link: (https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)
- PHP IntelliSense (Damjan Cvetko)  Link: (https://marketplace.visualstudio.com/items?itemName=zobo.php-intellisense)
- php cs fixer (junstyle) Link: (https://marketplace.visualstudio.com/items?itemName=junstyle.php-cs-fixer)
- PHP Snippets from PHPStorm (Phiter Fernandes) Link: (https://marketplace.visualstudio.com/items?itemName=phiter.phpstorm-snippets)
## Programas para el back-end

 Nodejs (https://nodejs.org/en/)
- Composer (https://getcomposer.org/)
- Para comprobar version Nodejs
- `npm --version`
- para comprobar version composer 
- `composer --version`









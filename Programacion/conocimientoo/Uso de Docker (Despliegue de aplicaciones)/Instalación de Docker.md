
### Instalación de Docker en Windows

#### Requisitos Previos

- **Windows 10 o superior** (versión Pro, Enterprise o Education) o **Windows 11**.
- Habilitar la virtualización en la BIOS de tu computadora.

#### Pasos de Instalación

1. **Descargar Docker Desktop**:
    - Ve a la página oficial de Docker Desktop y descarga el instalador para Windows.
    - 
1. **Instalar Docker Desktop**:
    - Ejecuta el instalador que descargaste.
    - Sigue las instrucciones en pantalla y asegúrate de habilitar la opción de "Usar WSL 2" si se te solicita.
    
1. **Iniciar Docker Desktop**:
    
    - Una vez instalado, abre Docker Desktop. Puede tardar unos minutos en iniciarse la primera vez.
    - Asegúrate de que Docker esté funcionando correctamente. Deberías ver un ícono de Docker en la bandeja del sistema.
    
1. **Verificar la instalación**:
    
    - Abre una terminal (puedes usar PowerShell o la terminal de Windows) y ejecuta:
        
        `docker --version`
        
    - También puedes probar ejecutando:
        
        `docker run hello-world`
        
    - Esto descargará una imagen de prueba y ejecutará un contenedor que imprime un mensaje de bienvenida.

### 2. Crear tu primera aplicación Docker

#### Estructura de Archivos

1. **Crear una carpeta para tu proyecto**:
    
    - Crea una carpeta en tu sistema, por ejemplo, `C:\docker-prueba`.
2. **Crear los archivos necesarios**:
    
    - Dentro de la carpeta, crea un archivo llamado `Dockerfile` y otro llamado `app.py`.

#### Contenido de los Archivos

- **`app.py`**:
    
    `1# app.py 2print("¡Hola desde Docker!")`
    
		- **`Dockerfile`**:
    
    
    `1# Dockerfile 2FROM python:3.9-slim 3COPY app.py / 4CMD ["python", "./app.py"]`
    

### 3. Construir y ejecutar la imagen

1. **Abrir la terminal**:
    
    - Navega a la carpeta donde creaste los archivos:
        
        `cd C:\docker-prueba`
        
2. **Construir la imagen**:
    
    - Ejecuta el siguiente comando en la terminal:
        
        `docker build -t python-test .`
        
3. **Ejecutar el contenedor**:
    
    - Una vez que la imagen se haya construido correctamente, ejecuta el contenedor:
        
        `docker run python-test`
        

### 4. Comandos útiles de Docker

- **Listar imágenes**:
    
    `docker image ls`
    
- **Eliminar una imagen**:
    
    `docker image rm [nombre de la imagen]`
    
- **Listar contenedores**:
    
    `docker ps -a`
    
- **Detener un contenedor**:
    
    `docker stop [nombre del contenedor]`
    
- **Ver logs de un contenedor**:
    
    `docker logs [nombre del contenedor]`
    

### 5. Recursos adicionales

- **Documentación oficial de Docker**: Docker Docs

Aquí tienes el texto refactorizado para mayor claridad y organización:

---

## Instalación de Docker en Windows

### Requisitos Previos

- **Windows 10 o superior** (versión Pro, Enterprise o Education) o **Windows 11**.
- Habilitar la virtualización en la BIOS de tu computadora.

### Pasos de Instalación

1. **Descargar Docker Desktop**:
   - Visita la [página oficial de Docker Desktop](https://www.docker.com/products/docker-desktop) y descarga el instalador para Windows.

2. **Instalar Docker Desktop**:
   - Ejecuta el instalador que descargaste.
   - Sigue las instrucciones en pantalla y asegúrate de habilitar la opción de "Usar WSL 2" si se te solicita.

3. **Iniciar Docker Desktop**:
   - Una vez instalado, abre Docker Desktop. Puede tardar unos minutos en iniciarse la primera vez.
   - Verifica que Docker esté funcionando correctamente. Deberías ver un ícono de Docker en la bandeja del sistema.

4. **Verificar la instalación**:
   - Abre una terminal (puedes usar PowerShell o la terminal de Windows) y ejecuta:
     ```bash
     docker --version
     ```
   - También puedes probar ejecutando:
     ```bash
     docker run hello-world
     ```
   - Esto descargará una imagen de prueba y ejecutará un contenedor que imprime un mensaje de bienvenida.



---

### Crear tu Primera Aplicación Docker

#### Estructura de Archivos

1. **Crear una Carpeta para tu Proyecto**:
   - Crea una carpeta en tu sistema, por ejemplo, `C:\docker-prueba`.

2. **Crear los Archivos Necesarios**:
   - Dentro de la carpeta, crea un archivo llamado `Dockerfile` y otro llamado `app.py`.

#### Contenido de los Archivos

- **`app.py`**:
    ```python
    # app.py
    print("¡Hola desde Docker!")
    ```

- **`Dockerfile`**:
    ```dockerfile
    # Dockerfile
    FROM python:3.9-slim
    COPY app.py /
    CMD ["python", "./app.py"]
    ```

---

### Construir y Ejecutar la Imagen

1. **Abrir la Terminal**:
   - Navega a la carpeta donde creaste los archivos:
     ```bash
     cd C:\docker-prueba
     ```

2. **Construir la Imagen**:
   - Ejecuta el siguiente comando en la terminal:
     ```bash
     docker build -t python-test .
     ```

3. **Ejecutar el Contenedor**:
   - Una vez que la imagen se haya construido correctamente, ejecuta el contenedor:
     ```bash
     docker run python-test
     ```

---

### Comandos Útiles de Docker

- **Listar Imágenes**:
  ```bash
  docker image ls
  ```

- **Eliminar una Imagen**:
  ```bash
  docker image rm [nombre de la imagen]
  ```

- **Listar Contenedores**:
  ```bash
  docker ps -a
  ```

- **Detener un Contenedor**:
  ```bash
  docker stop [nombre del contenedor]
  ```

- **Ver Logs de un Contenedor**:
  ```bash
  docker logs [nombre del contenedor]
  ```

---

### Recursos Adicionales

- **Documentación Oficial de Docker**: [Docker Docs](https://docs.docker.com/)

---

Este formato mejora la legibilidad y organiza la información de manera más efectiva, facilitando la comprensión de los pasos para instalar y utilizar Docker en Windows.
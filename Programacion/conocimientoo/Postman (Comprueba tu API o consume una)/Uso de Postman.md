
Para usar Postman con todos los métodos HTTP, primero debes crear una nueva solicitud en tu espacio de trabajo. Luego, selecciona el método que deseas utilizar, como GET, POST, PUT, PATCH, DELETE, HEAD u OPTIONS. Cada método tiene un propósito específico:

- **GET**: Para obtener datos del servidor. Se utiliza para solicitar información sin modificar el estado del recurso.
    
- **POST**: Para enviar datos al servidor, como crear un nuevo recurso. Este método se utiliza comúnmente para enviar formularios o datos JSON.
    
- **PUT**: Para actualizar un recurso existente en el servidor. Se utiliza para reemplazar completamente el recurso especificado.
    
- **PATCH**: Similar a PUT, pero se utiliza para realizar actualizaciones parciales en un recurso existente.
    
- **DELETE**: Para eliminar un recurso del servidor. Este método solicita la eliminación del recurso especificado.
    
- **HEAD**: Similar a GET, pero solo solicita los encabezados de la respuesta sin el cuerpo. Se utiliza para obtener metadatos.
    
- **OPTIONS**: Para describir las opciones de comunicación para el recurso de destino. Este método permite conocer qué métodos HTTP son compatibles con el recurso.
    

### Pasos para usar Postman con diferentes métodos

1. **Crear una nueva solicitud**:
    
    - Abre Postman y selecciona "Nueva solicitud".
    - Asigna un nombre y guarda la solicitud en una colección.
2. **Seleccionar el método HTTP**:
    
    - En la parte superior izquierda, selecciona el método deseado del menú desplegable.
3. **Ingresar la URL**:
    
    - Escribe la URL del endpoint de la API al que deseas hacer la solicitud.
4. **Configurar los encabezados**:
    
    - Si es necesario, agrega encabezados como `Content-Type` o `Authorization` en la pestaña "Headers".
5. **Agregar el cuerpo de la solicitud**:
    
    - Para métodos como POST, PUT o PATCH, selecciona la pestaña "Body" y elige el formato adecuado (por ejemplo, `raw` y `JSON`).
6. **Enviar la solicitud**:
    
    - Haz clic en el botón "Enviar" para realizar la solicitud y ver la respuesta del servidor.
7. **Revisar la respuesta**:
    
    - Observa el código de estado HTTP y el cuerpo de la respuesta en la sección inferior de Postman.

### Ejemplos de solicitudes

- **Ejemplo de solicitud GET**:

`GET /api/v1/usuarios HTTP/1.1 2Host: ejemplo.com 3Content-Type: application/json`

- **Ejemplo de solicitud POST**:

`POST /api/v1/usuarios HTTP/1.1 2Host: ejemplo.com 3Content-Type: application/json 4 5{ 6  "nombre": "Juan", 7  "email": "juan@ejemplo.com" 8}`

- **Ejemplo de solicitud PUT**:

`PUT /api/v1/usuarios/1 HTTP/1.1 2Host: ejemplo.com 3Content-Type: application/json 4 5{ 6  "nombre": "Juan Actualizado" 7}`

- **Ejemplo de solicitud DELETE**:

`DELETE /api/v1/usuarios/1 HTTP/1.1 2Host: ejemplo.com`
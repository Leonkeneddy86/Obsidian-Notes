


---

## Uso de Postman con Métodos HTTP

Para utilizar Postman con todos los métodos HTTP, primero debes crear una nueva solicitud en tu espacio de trabajo. Luego, selecciona el método que deseas utilizar, como GET, POST, PUT, PATCH, DELETE, HEAD u OPTIONS. A continuación, se describe el propósito de cada método:

- **GET**: Obtiene datos del servidor sin modificar el estado del recurso.
  
- **POST**: Envía datos al servidor para crear un nuevo recurso, comúnmente utilizado para enviar formularios o datos JSON.
  
- **PUT**: Actualiza un recurso existente en el servidor, reemplazando completamente el recurso especificado.
  
- **PATCH**: Realiza actualizaciones parciales en un recurso existente.
  
- **DELETE**: Elimina un recurso del servidor, solicitando la eliminación del recurso especificado.
  
- **HEAD**: Similar a GET, pero solo solicita los encabezados de la respuesta sin el cuerpo, utilizado para obtener metadatos.
  
- **OPTIONS**: Describe las opciones de comunicación para el recurso de destino, permitiendo conocer qué métodos HTTP son compatibles.

### Pasos para Usar Postman con Diferentes Métodos

1. **Crear una Nueva Solicitud**:
   - Abre Postman y selecciona "Nueva solicitud".
   - Asigna un nombre y guarda la solicitud en una colección.

2. **Seleccionar el Método HTTP**:
   - En la parte superior izquierda, selecciona el método deseado del menú desplegable.

3. **Ingresar la URL**:
   - Escribe la URL del endpoint de la API al que deseas hacer la solicitud.

4. **Configurar los Encabezados**:
   - Si es necesario, agrega encabezados como `Content-Type` o `Authorization` en la pestaña "Headers".

5. **Agregar el Cuerpo de la Solicitud**:
   - Para métodos como POST, PUT o PATCH, selecciona la pestaña "Body" y elige el formato adecuado (por ejemplo, `raw` y `JSON`).

6. **Enviar la Solicitud**:
   - Haz clic en el botón "Enviar" para realizar la solicitud y ver la respuesta del servidor.

7. **Revisar la Respuesta**:
   - Observa el código de estado HTTP y el cuerpo de la respuesta en la sección inferior de Postman.

### Ejemplos de Solicitudes

- **Ejemplo de Solicitud GET**:
    ```
    GET /api/v1/usuarios HTTP/1.1
    Host: ejemplo.com
    Content-Type: application/json
    ```

- **Ejemplo de Solicitud POST**:
    ```
    POST /api/v1/usuarios HTTP/1.1
    Host: ejemplo.com
    Content-Type: application/json

    {
        "nombre": "Juan",
        "email": "juan@ejemplo.com"
    }
    ```

- **Ejemplo de Solicitud PUT**:
    ```
    PUT /api/v1/usuarios/1 HTTP/1.1
    Host: ejemplo.com
    Content-Type: application/json

    {
        "nombre": "Juan Actualizado"
    }
    ```

- **Ejemplo de Solicitud DELETE**:
    ```
    DELETE /api/v1/usuarios/1 HTTP/1.1
    Host: ejemplo.com
    ```

---


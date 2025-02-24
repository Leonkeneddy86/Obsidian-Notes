# Rest Controllers en Spring Boot

## **1. ¿Qué es un Controller en Spring Boot?**

Un **Controller** en Spring Boot es una clase que maneja las **solicitudes HTTP** entrantes, procesa la lógica necesaria y devuelve una **respuesta** al cliente. Es el intermediario entre el cliente (como un navegador web o una aplicación móvil) y la lógica de negocio de tu aplicación.

### **Funciones Principales de un Controller:**

- **Mapear solicitudes HTTP** a métodos específicos.
- **Procesar datos** recibidos en las solicitudes.
- **Retornar respuestas** al cliente en formatos como JSON, XML o texto plano.

## **2. Crear un REST Controller**

Para crear una **API REST** en Spring Boot, utilizamos la anotación `@RestController`. Esta anotación combina `@Controller` y `@ResponseBody`, lo que significa que los métodos dentro del Controller retornarán datos directamente en la respuesta HTTP, en lugar de vistas HTML.

### **Pasos para Crear un REST Controller:**

1. **Crear una Clase Controller:**
    - Dentro del paquete adecuado (por ejemplo, `com.ejemplo.miapi.controller`), crea una clase Java que actuará como tu Controller.
2. **Anotar la Clase con `@RestController`:**
    - Esto indica a Spring que la clase manejará solicitudes HTTP y retornará respuestas en formato JSON, XML o texto.
3. **Definir una Ruta Base con `@RequestMapping`:**
    - Esta anotación establece una ruta base para todos los endpoints dentro del Controller.

### **Ejemplo:**

```java

package com.ejemplo.miapi.controller;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/v1/")
public class ApiController {

    // Métodos de endpoints irán aquí

}
```

---

## **3. Añadir Endpoints Básicos**

Los **endpoints** son rutas específicas que manejan diferentes tipos de solicitudes HTTP (GET, POST, etc.). A continuación, veremos cómo añadir los endpoints básicos utilizando cadenas de texto para las solicitudes y respuestas.

### **3.1. GET Endpoint**

**Objetivo:** Manejar solicitudes HTTP GET para obtener información.

**Anotación Utilizada:** `@GetMapping`

**Método Básico:**

```java
@GetMapping("/mensaje")
public String obtenerMensaje() {
    return "¡Hola! Este es un mensaje de la API.";
}
```

**Explicación:**

- **`@GetMapping("/mensaje")`**: Mapea las solicitudes GET a la ruta `/api/mensaje`.
- **Método `obtenerMensaje`**: Retorna una cadena de texto simple como respuesta.

### **3.2. POST Endpoint**

**Objetivo:** Manejar solicitudes HTTP POST para recibir datos del cliente.

**Anotación Utilizada:** `@PostMapping`

**Método Básico:**

```java
@PostMapping("/mensaje")
public String recibirMensaje(@RequestBody String mensaje) {
    return "Mensaje recibido: " + mensaje;
}
```

**Explicación:**

- **`@PostMapping("/mensaje")`**: Mapea las solicitudes POST a la ruta `/api/mensaje`.
- **`@RequestBody String mensaje`**: Indica que el cuerpo de la solicitud HTTP será una cadena de texto que se asignará al parámetro `mensaje`.
- **Método `recibirMensaje`**: Retorna una confirmación con el mensaje recibido.

### **3.3. PUT Endpoint**

**Objetivo:** Manejar solicitudes HTTP PUT para actualizar información existente.

**Anotación Utilizada:** `@PutMapping`

**Método Básico:**

```java
@PutMapping("/mensaje/{id}")
public String actualizarMensaje(@PathVariable int id, @RequestBody String mensaje) {
    if (id == 1) {
        return "Mensaje actualizado a: " + mensaje;
    }
    return "Mensaje no encontrado";
    
}
```

**Explicación:**

- **`@PutMapping("/mensaje/{id}")`**: Mapea las solicitudes PUT a la ruta `/api/mensaje/{id}`.
- **`@PathVariable int id`**: Extrae el valor `id` de la ruta y lo asigna al parámetro del método.
- **`@RequestBody String mensaje`**: Indica que el cuerpo de la solicitud HTTP será una cadena de texto que se asignará al parámetro `mensaje`.
- **Método `actualizarMensaje`**: Actualiza el mensaje si el `id` es `1`; de lo contrario, indica que el mensaje no fue encontrado.

### **3.4. DELETE Endpoint**

**Objetivo:** Manejar solicitudes HTTP DELETE para eliminar información existente.

**Anotación Utilizada:** `@DeleteMapping`

**Método Básico:**

```java
@DeleteMapping("/mensaje/{id}")
public String eliminarMensaje(@PathVariable int id) {
    if (id == 1) {
        return "Mensaje con ID " + id + " eliminado.";
    } else {
        return "Mensaje no encontrado.";
    }
}
```

**Explicación:**

- **`@DeleteMapping("/mensaje/{id}")`**: Mapea las solicitudes DELETE a la ruta `/api/mensaje/{id}`.
- **`@PathVariable int id`**: Extrae el valor `id` de la ruta y lo asigna al parámetro del método.
- **Método `eliminarMensaje`**: Elimina el mensaje si el `id` es `1`; de lo contrario, indica que el mensaje no fue encontrado.

---

## **4. Manejo de Respuestas HTTP**

En el desarrollo de APIs REST con Spring Boot, es fundamental manejar adecuadamente las respuestas HTTP para comunicar de manera efectiva el resultado de las solicitudes al cliente. Esto incluye el uso correcto de los **códigos de estado HTTP** y la utilización de la clase **`ResponseEntity`** para personalizar las respuestas.

### **4.1. Códigos de Estado HTTP**

Los **códigos de estado HTTP** son respuestas estándar que indican el resultado de una solicitud HTTP realizada al servidor. Estos códigos ayudan a los clientes a entender si una solicitud fue exitosa, si hubo algún error o si se requiere alguna acción adicional.

A continuación, se presenta un **cuadro resumen** de los códigos de estado HTTP más comunes utilizados en APIs REST:

| **Código** | **Nombre** | **Descripción** | **Uso Común en APIs REST** |
| --- | --- | --- | --- |
| **200** | **OK** | La solicitud ha tenido éxito. | Respuestas exitosas a solicitudes GET, PUT o DELETE. |
| **201** | **Created** | La solicitud ha sido cumplida y ha resultado en la creación de un nuevo recurso. | Respuestas exitosas a solicitudes POST que crean nuevos recursos. |
| **400** | **Bad Request** | El servidor no puede o no procesará la solicitud debido a algo que es percibido como un error del cliente (por ejemplo, sintaxis inválida). | Cuando los datos enviados por el cliente son inválidos o faltan parámetros requeridos. |
| **401** | **Unauthorized** | La solicitud requiere autenticación del usuario. | Cuando el cliente intenta acceder a un recurso protegido sin credenciales válidas. |
| **403** | **Forbidden** | El servidor entendió la solicitud, pero se niega a autorizarla. | Cuando el usuario autenticado no tiene permisos para acceder al recurso solicitado. |
| **404** | **Not Found** | El servidor no encontró nada que coincida con la URI de la solicitud. | Cuando el recurso solicitado no existe en el servidor. |
| **500** | **Internal Server Error** | El servidor encontró una condición inesperada que le impidió cumplir con la solicitud. | Errores inesperados del servidor, como excepciones no manejadas. |
| **503** | **Service Unavailable** | El servidor no está listo para manejar la solicitud. | Cuando el servidor está sobrecargado o en mantenimiento. |

### **4.2. ¿Qué es `ResponseEntity`?**

**`ResponseEntity`** es una clase de Spring que representa toda la **respuesta HTTP**, incluyendo el **cuerpo**, los **encabezados** y el **código de estado**. Permite una mayor flexibilidad y control sobre las respuestas que se envían al cliente, en comparación con simplemente retornar un objeto o una cadena de texto.

### **Funciones Principales de `ResponseEntity`:**

- **Controlar el Código de Estado HTTP:** Permite especificar explícitamente el código de estado de la respuesta.
- **Agregar Encabezados Personalizados:** Facilita la inclusión de encabezados HTTP adicionales en la respuesta.
- **Retornar un Cuerpo de Respuesta Personalizado:** Permite enviar datos estructurados (como JSON) en el cuerpo de la respuesta.

### **4.3. Cómo Funciona `ResponseEntity`**

Cuando un método en un **Controller** retorna una instancia de `ResponseEntity`, Spring Boot utiliza esta instancia para construir la respuesta HTTP que se enviará al cliente. Esto incluye el cuerpo de la respuesta, los encabezados y el código de estado especificados.

### **4.4. Cómo Crear y Utilizar `ResponseEntity`**

### **1. Retornar una Respuesta Exitosa con `200 OK`**

```java
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api")
public class ApiController {

    // GET Endpoint: /api/mensaje
    @GetMapping("/mensaje")
    public ResponseEntity<String> obtenerMensaje() {
        String mensaje = "¡Hola! Este es un mensaje de la API.";
        return new ResponseEntity<>(mensaje, HttpStatus.OK);
    }
}
```

**Explicación:**

- **Cuerpo de la Respuesta:** `"¡Hola! Este es un mensaje de la API."`
- **Código de Estado HTTP:** `200 OK`

### **2. Retornar una Respuesta de Creación con `201 Created`**

```java
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api")
public class ApiController {

    // POST Endpoint: /api/mensaje
    @PostMapping("/mensaje")
    public ResponseEntity<String> crearMensaje(@RequestBody String mensaje) {
        // Lógica para crear el mensaje (omisión por simplicidad)
        String respuesta = "Mensaje creado: " + mensaje;
        return new ResponseEntity<>(respuesta, HttpStatus.CREATED);
    }
}
```

**Explicación:**

- **Cuerpo de la Respuesta:** `"Mensaje creado: [mensaje recibido]"`
- **Código de Estado HTTP:** `201 Created`

### **3. Retornar un Error con `404 Not Found`**

```java
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api")
public class ApiController {

    // GET Endpoint con Path Variable: /api/mensaje/{id}
    @GetMapping("/mensaje/{id}")
    public ResponseEntity<String> obtenerMensajePorId(@PathVariable int id) {
        if (id == 1) { // Simulación de búsqueda exitosa
            String mensaje = "Mensaje encontrado: ¡Hola!";
            return new ResponseEntity<>(mensaje, HttpStatus.OK);
        } else {
            String error = "Mensaje no encontrado";
            return new ResponseEntity<>(error, HttpStatus.NOT_FOUND);
        }
    }
}
```

**Explicación:**

- **Si `id == 1`:**
    - **Cuerpo de la Respuesta:** `"Mensaje encontrado: ¡Hola!"`
    - **Código de Estado HTTP:** `200 OK`
- **Si `id != 1`:**
    - **Cuerpo de la Respuesta:** `"Mensaje no encontrado"`
    - **Código de Estado HTTP:** `404 Not Found`

### **4. Retornar una Respuesta con Encabezados Personalizados**

```java
import org.springframework.http.HttpHeaders;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api")
public class ApiController {

    // GET Endpoint con Encabezados Personalizados: /api/mensaje/cabecera
    @GetMapping("/mensaje/cabecera")
    public ResponseEntity<String> obtenerMensajeConCabecera() {
        String mensaje = "Mensaje con encabezado personalizado.";

        HttpHeaders headers = new HttpHeaders();
        headers.add("Custom-Header", "ValorPersonalizado");

        return new ResponseEntity<>(mensaje, headers, HttpStatus.OK);
    }
}
```

**Explicación:**

- **Cuerpo de la Respuesta:** `"Mensaje con encabezado personalizado."`
- **Encabezados:** `Custom-Header: ValorPersonalizado`
- **Código de Estado HTTP:** `200 OK`

### **4.5. Resumen de Uso de `ResponseEntity`**

| **Situación** | **Método HTTP** | **Código de Estado HTTP** | **Uso de `ResponseEntity`** |
| --- | --- | --- | --- |
| Solicitud exitosa y retorno de datos | GET | `200 OK` | `return new ResponseEntity<>(datos, HttpStatus.OK);` |
| Creación exitosa de un recurso | POST | `201 Created` | `return new ResponseEntity<>(mensajeCreacion, HttpStatus.CREATED);` |
| Recurso no encontrado | GET, PUT, DELETE | `404 Not Found` | `return new ResponseEntity<>(mensajeError, HttpStatus.NOT_FOUND);` |
| Error interno del servidor | Cualquier | `500 Internal Server Error` | `return new ResponseEntity<>(mensajeError, HttpStatus.INTERNAL_SERVER_ERROR);` |
| Solicitud inválida del cliente | POST, PUT | `400 Bad Request` | `return new ResponseEntity<>(mensajeError, HttpStatus.BAD_REQUEST);` |

### **4.6. Ventajas de Utilizar `ResponseEntity`**

- **Flexibilidad en las Respuestas:** Permite personalizar el cuerpo, los encabezados y el código de estado de la respuesta.
- **Claridad en la Comunicación:** Facilita la comunicación clara del resultado de la solicitud al cliente mediante códigos de estado apropiados.
- **Manejo Centralizado de Errores:** Facilita la implementación de manejadores de excepciones globales que retornan `ResponseEntity` con mensajes y códigos de estado consistentes.
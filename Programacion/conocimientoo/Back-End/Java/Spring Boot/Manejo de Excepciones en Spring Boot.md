# Manejo de Excepciones en Spring Boot

El manejo de excepciones en Spring Boot es esencial para crear aplicaciones robustas y proporcionar una experiencia de usuario coherente. Spring Boot ofrece herramientas para manejar excepciones de forma centralizada utilizando `@ControllerAdvice` y `@ExceptionHandler`.

### 1. Manejo de Excepciones Específicas

Para manejar excepciones específicas dentro de un controlador, puedes usar la anotación `@ExceptionHandler`. Esto permite capturar y gestionar excepciones lanzadas por los métodos del controlador.

### Ejemplo Básico

```java
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;

@RestController
@RequestMapping("/api")
public class MyController {

    @GetMapping("/data")
    public String getData() {
        if (true) { // Simulación de una condición que lanza una excepción
            throw new MyCustomException("Error occurred while fetching data");
        }
        return "Some data";
    }

    @ExceptionHandler(MyCustomException.class)
    public ResponseEntity<String> handleMyCustomException(MyCustomException ex) {
        return new ResponseEntity<>(ex.getMessage(), HttpStatus.BAD_REQUEST);
    }
}

class MyCustomException extends RuntimeException {
    public MyCustomException(String message) {
        super(message);
    }
}

```

En este ejemplo, `MyCustomException` es manejada específicamente por el método `handleMyCustomException` dentro del mismo controlador.

### 2. Manejo de Excepciones Globales

Para manejar excepciones de forma centralizada y global en toda la aplicación, se utiliza `@ControllerAdvice` junto con `@ExceptionHandler`. Esto permite definir un manejador de excepciones que se aplica a todos los controladores.

### Ejemplo de Manejo Global de Excepciones

1. **Clase `@ControllerAdvice`**:

```java
import org.springframework.web.bind.annotation.ControllerAdvice;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;

@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(MyCustomException.class)
    public ResponseEntity<String> handleMyCustomException(MyCustomException ex) {
        return new ResponseEntity<>(ex.getMessage(), HttpStatus.BAD_REQUEST);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleGeneralException(Exception ex) {
        return new ResponseEntity<>("An error occurred: " + ex.getMessage(), HttpStatus.INTERNAL_SERVER_ERROR);
    }
}

```

1. **Controlador**:

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/api")
public class MyController {

    @GetMapping("/data")
    public String getData() {
        if (true) { // Simulación de una condición que lanza una excepción
            throw new MyCustomException("Error occurred while fetching data");
        }
        return "Some data";
    }
}

class MyCustomException extends RuntimeException {
    public MyCustomException(String message) {
        super(message);
    }
}

```

En este ejemplo, `GlobalExceptionHandler` maneja `MyCustomException` y cualquier otra excepción no específica en toda la aplicación.

### 3. Personalización de la Respuesta de Error

Para proporcionar respuestas de error más estructuradas y personalizadas, puedes crear una clase que represente el cuerpo de la respuesta de error.

### Ejemplo de Respuesta de Error Personalizada

1. **Clase de Respuesta de Error**:

```java

public class ErrorResponse {
    private String message;
    private String details;

    public ErrorResponse(String message, String details) {
        this.message = message;
        this.details = details;
    }

    // Getters y setters
}

```

1. **Clase `@ControllerAdvice` con Respuesta Personalizada**:

```java

import org.springframework.web.bind.annotation.ControllerAdvice;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;

@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(MyCustomException.class)
    public ResponseEntity<ErrorResponse> handleMyCustomException(MyCustomException ex) {
        ErrorResponse errorResponse = new ErrorResponse(ex.getMessage(), "Details about the error");
        return new ResponseEntity<>(errorResponse, HttpStatus.BAD_REQUEST);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<ErrorResponse> handleGeneralException(Exception ex) {
        ErrorResponse errorResponse = new ErrorResponse("An error occurred", ex.getMessage());
        return new ResponseEntity<>(errorResponse, HttpStatus.INTERNAL_SERVER_ERROR);
    }
}

```

### 4. Registro de Excepciones

Para registrar excepciones para propósitos de monitoreo y depuración, puedes integrar un logger en tu manejador de excepciones.

### Ejemplo de Registro de Excepciones

```jsx

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.web.bind.annotation.ControllerAdvice;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;

@ControllerAdvice
public class GlobalExceptionHandler {

    private static final Logger logger = LoggerFactory.getLogger(GlobalExceptionHandler.class);

    @ExceptionHandler(MyCustomException.class)
    public ResponseEntity<ErrorResponse> handleMyCustomException(MyCustomException ex) {
        logger.error("Custom Exception: ", ex);
        ErrorResponse errorResponse = new ErrorResponse(ex.getMessage(), "Details about the error");
        return new ResponseEntity<>(errorResponse, HttpStatus.BAD_REQUEST);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<ErrorResponse> handleGeneralException(Exception ex) {
        logger.error("General Exception: ", ex);
        ErrorResponse errorResponse = new ErrorResponse("An error occurred", ex.getMessage());
        return new ResponseEntity<>(errorResponse, HttpStatus.INTERNAL_SERVER_ERROR);
    }
}

```
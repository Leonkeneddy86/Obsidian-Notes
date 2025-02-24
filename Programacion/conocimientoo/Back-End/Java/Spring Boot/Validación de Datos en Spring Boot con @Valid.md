# Validación de Datos en Spring Boot con @Valid

### Validación de Datos en Spring Boot: Uso de `@Valid` y el Paquete `javax.validation`

La validación de datos de entrada es crucial para asegurar que las aplicaciones manejen correctamente los datos que reciben. Spring Boot facilita la validación utilizando el paquete `javax.validation` (también conocido como Bean Validation) y la anotación `@Valid`.

### 1. Configuración de Dependencias

Antes de empezar, asegúrate de tener las dependencias necesarias en tu proyecto. Si estás usando Maven, añade las siguientes dependencias en tu `pom.xml`:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-validation</artifactId>
</dependency>

```

Para Gradle, añade las siguientes dependencias en tu `build.gradle`:

```groovy

implementation 'org.springframework.boot:spring-boot-starter-web'
implementation 'org.springframework.boot:spring-boot-starter-validation'

```

### 2. Definición del Modelo con Anotaciones de Validación

Utiliza las anotaciones de validación de `javax.validation` para definir las reglas de validación en tu modelo. Aquí tienes un ejemplo de un modelo `User` con validaciones:

```java

import javax.validation.constraints.Email;
import javax.validation.constraints.NotEmpty;
import javax.validation.constraints.Size;

public class User {

    @NotEmpty(message = "Name is mandatory")
    @Size(min = 2, max = 30, message = "Name must be between 2 and 30 characters")
    private String name;

    @NotEmpty(message = "Email is mandatory")
    @Email(message = "Email should be valid")
    private String email;

    // Getters y setters
}

```

### 3. Uso de `@Valid` en Controladores

En tus controladores, utiliza la anotación `@Valid` para activar la validación del modelo de datos entrante. Si la validación falla, se lanzará una excepción `MethodArgumentNotValidException`, que puede ser manejada para devolver una respuesta adecuada.

```java

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.validation.FieldError;
import org.springframework.web.bind.MethodArgumentNotValidException;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import javax.validation.Valid;
import java.util.HashMap;
import java.util.Map;

@RestController
@RequestMapping("/api/users")
public class UserController {

    @PostMapping
    public ResponseEntity<String> createUser(@Valid @RequestBody User user) {
        // Procesar el usuario
        return ResponseEntity.ok("User is valid");
    }

    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<Map<String, String>> handleValidationExceptions(MethodArgumentNotValidException ex) {
        Map<String, String> errors = new HashMap<>();
        ex.getBindingResult().getAllErrors().forEach((error) -> {
            String fieldName = ((FieldError) error).getField();
            String errorMessage = error.getDefaultMessage();
            errors.put(fieldName, errorMessage);
        });
        return new ResponseEntity<>(errors, HttpStatus.BAD_REQUEST);
    }
}

```

### 4. Personalización de Mensajes de Error

Los mensajes de error pueden ser personalizados utilizando archivos de mensajes. Crea un archivo `messages.properties` en `src/main/resources` y define tus mensajes de error personalizados:

```java
name.notempty=Name is mandatory
name.size=Name must be between 2 and 30 characters
email.notempty=Email is mandatory
email.valid=Email should be valid

```

Luego, en tu modelo, referencia estos mensajes personalizados:

```java

import javax.validation.constraints.Email;
import javax.validation.constraints.NotEmpty;
import javax.validation.constraints.Size;

public class User {

    @NotEmpty(message = "{name.notempty}")
    @Size(min = 2, max = 30, message = "{name.size}")
    private String name;

    @NotEmpty(message = "{email.notempty}")
    @Email(message = "{email.valid}")
    private String email;

    // Getters y setters
}
```
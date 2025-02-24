# Patrón DTO (Data Transfer Object) en Spring Boot

El patrón DTO (Data Transfer Object) se utiliza para transferir datos entre capas de una aplicación. En Spring Boot, los DTOs son especialmente útiles para manejar datos de entrada y salida (requests y responses) sin exponer las entidades directamente, lo que mejora la encapsulación y la seguridad.

### 1. Uso de DTOs en Spring Boot

### a. DTO para Requests y Responses

Un DTO se puede utilizar para:

- **Requests**: Capturar datos de entrada de una solicitud HTTP.
- **Responses**: Enviar datos de salida en una respuesta HTTP.

### b. Ventajas del Uso de DTOs

- **Encapsulación**: Oculta los detalles internos de la entidad.
- **Validación**: Facilita la validación de datos de entrada.
- **Transformación de Datos**: Permite transformar datos antes de enviarlos o almacenarlos.

### 2. Creación de DTOs con Lombok y Records

### a. Uso de Lombok

**Request DTO**

```java
import lombok.Data;
import javax.validation.constraints.NotEmpty;

@Data
public class BookRequestDTO {

    @NotEmpty(message = "Title is required")
    private String title;

    @NotEmpty(message = "Author is required")
    private String author;
}

```

**Response DTO**

```java
import lombok.Data;

@Data
public class BookResponseDTO {

    private Long id;
    private String title;
    private String author;
}

```

### b. Uso de Records (Java 16+)

**Request DTO**

```java
import javax.validation.constraints.NotEmpty;

public record BookRequestDTO(
    @NotEmpty(message = "Title is required") String title,
    @NotEmpty(message = "Author is required") String author
) {}

```

**Response DTO**

```java
public record BookResponseDTO(
    Long id,
    String title,
    String author
) {}

```
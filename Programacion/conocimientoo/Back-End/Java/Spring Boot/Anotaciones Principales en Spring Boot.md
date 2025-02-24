# Anotaciones Principales en Spring Boot

Las anotaciones en Spring Boot son una parte fundamental del framework, ya que permiten configurar y gestionar los componentes de la aplicación de manera declarativa. A continuación, se explican en detalle algunas de las anotaciones más importantes y su uso.

### 1. `@SpringBootApplication`

La anotación `@SpringBootApplication` se coloca en la clase principal de una aplicación Spring Boot. Esta anotación es una combinación de tres anotaciones cruciales:

- `@SpringBootConfiguration`: Indica que esta es una clase de configuración de Spring Boot.
- `@EnableAutoConfiguration`: Habilita la auto-configuración de Spring Boot, lo que permite que el framework configure automáticamente la aplicación según las dependencias encontradas en el classpath.
- `@ComponentScan`: Habilita el escaneo de componentes, permitiendo a Spring encontrar y registrar automáticamente los beans en el contexto de la aplicación.

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MyAppApplication {
    public static void main(String[] args) {
        SpringApplication.run(MyAppApplication.class, args);
    }
}

```

### 2. `@Component`

La anotación `@Component` indica que una clase es un componente de Spring. Esta anotación se utiliza para marcar clases que deben ser gestionadas por el contenedor de Spring. Es una anotación genérica que se puede utilizar en cualquier clase.

```java
import org.springframework.stereotype.Component;

@Component
public class MyComponent {
    public void doSomething() {
        System.out.println("Doing something...");
    }
}
```

### 3. `@Service`

La anotación `@Service` es una especialización de `@Component` que se utiliza para marcar las clases de servicio. Los servicios contienen la lógica de negocio de la aplicación.

```java
import org.springframework.stereotype.Service;

@Service
public class MyService {
    public void performService() {
        System.out.println("Service is being performed...");
    }
}
```

### 4. `@Repository`

La anotación `@Repository` es otra especialización de `@Component` y se utiliza para marcar las clases de acceso a datos, también conocidas como repositorios. Además de marcar la clase como un bean, `@Repository` también traduce automáticamente las excepciones específicas de la base de datos a excepciones de Spring.

```java
javaCopy code
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface MyRepository extends JpaRepository<MyEntity, Long> {
}

```

### 5. `@Controller`

La anotación `@Controller` se utiliza para marcar las clases que manejan las solicitudes web (HTTP). Estas clases son responsables de procesar las solicitudes entrantes, invocar la lógica de negocio correspondiente y devolver la respuesta adecuada.

```java
javaCopy code
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class MyController {
    @GetMapping("/hello")
    public String sayHello(Model model) {
        model.addAttribute("message", "Hello, Spring MVC!");
        return "hello";
    }
}

```

### 6. `@RestController`

La anotación `@RestController` es una combinación de `@Controller` y `@ResponseBody`. Se utiliza para simplificar la creación de controladores RESTful, ya que automáticamente serializa los objetos devueltos como JSON o XML.

```java
javaCopy code
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MyRestController {
    @GetMapping("/api/hello")
    public String sayHello() {
        return "Hello, RESTful Spring!";
    }
}

```

### 7. `@Autowired`

La anotación `@Autowired` se utiliza para inyectar automáticamente las dependencias de un bean. Spring resolverá y autoconfigurará el bean necesario para la dependencia marcada con esta anotación.

```java
javaCopy code
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class MyComponent {
    private final MyService myService;

    @Autowired
    public MyComponent(MyService myService) {
        this.myService = myService;
    }

    public void useService() {
        myService.performService();
    }
}

```

### 8. `@Configuration`

La anotación `@Configuration` se utiliza para definir una clase de configuración que puede contener uno o más métodos anotados con `@Bean`. Estos métodos producen beans que se gestionarán por el contenedor de Spring.

```java
javaCopy code
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {
    @Bean
    public MyService myService() {
        return new MyService();
    }
}

```

### 9. `@Bean`

La anotación `@Bean` se utiliza dentro de una clase marcada con `@Configuration` para definir un bean que debe ser gestionado por el contenedor de Spring.

```java
javaCopy code
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {
    @Bean
    public MyService myService() {
        return new MyService();
    }
}

```

### 10. `@Value`

La anotación `@Value` se utiliza para inyectar valores de propiedades en beans de Spring. Estos valores pueden provenir de archivos de configuración como `application.properties` o variables de entorno.

```java
javaCopy code
import org.springframework.beans.factory.annotation.Value;
import org.springframework.stereotype.Component;

@Component
public class MyComponent {
    @Value("${my.property}")
    private String myProperty;

    public void printProperty() {
        System.out.println("Property value: " + myProperty);
    }
}

```

### 11. `@RequestMapping`

La anotación `@RequestMapping` se utiliza para mapear solicitudes web a métodos específicos en un controlador. Puede especificar la URL, el método HTTP, los parámetros, los encabezados y más.

```java
javaCopy code
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MyRestController {
    @RequestMapping(value = "/api/hello", method = RequestMethod.GET)
    public String sayHello() {
        return "Hello, RESTful Spring!";
    }
}

```

### 12. `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`

Estas anotaciones son atajos para `@RequestMapping` para los métodos HTTP GET, POST, PUT y DELETE, respectivamente.

```java
javaCopy code
import org.springframework.web.bind.annotation.*;

@RestController
public class MyRestController {
    @GetMapping("/api/hello")
    public String getHello() {
        return "Hello, GET!";
    }

    @PostMapping("/api/hello")
    public String postHello() {
        return "Hello, POST!";
    }

    @PutMapping("/api/hello")
    public String putHello() {
        return "Hello, PUT!";
    }

    @DeleteMapping("/api/hello")
    public String deleteHello() {
        return "Hello, DELETE!";
    }
}

```
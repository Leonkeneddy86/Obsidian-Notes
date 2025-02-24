# Beans y su ciclo de vida

- Content

### 1. **Introducción a los Beans en Spring**

- **Concepto**: Un bean en Spring es un objeto que el contenedor de Spring administra. Estos beans son instanciados, configurados y ensamblados por el contenedor, lo que permite a Spring manejar su ciclo de vida, inyección de dependencias y configuración. Los beans son los bloques de construcción de cualquier aplicación Spring.
- **¿Por qué se utilizan?**: El uso de beans permite a Spring gestionar los objetos de la aplicación de manera centralizada, facilitando la separación de responsabilidades, la modularización y la reutilización de código. Al tener un contenedor de Spring que controla los beans, se promueve el desarrollo desacoplado y fácilmente testeable.

### 2. **Ciclo de Vida de un Bean**

El ciclo de vida de un bean en Spring es crucial para entender cómo y cuándo se crean, inicializan y destruyen los beans. A continuación se detallan las fases clave:

- **Instanciación**:
    - **Qué ocurre**: Spring crea una instancia del bean. Esto sucede cuando el contenedor necesita satisfacer una dependencia o cuando se solicita explícitamente un bean del contexto de aplicación.
    - **Cuándo se usa**: La instancia del bean se crea en el momento en que otro bean requiere su uso o cuando el contexto se inicia (en el caso de beans de tipo Singleton).
- **Población de Propiedades**:
    - **Qué ocurre**: Una vez que el bean ha sido instanciado, Spring inyecta las dependencias (otros beans, valores de configuración, etc.) en sus propiedades, ya sea a través del constructor, setters o directamente en los campos.
    - **Cuándo se usa**: Esto es automático y ocurre durante la fase de inicialización del bean, justo después de su creación.
    
    ```java
    
    @Component
    public class MyBean {
    
        private MyDependency myDependency;
    
        // Inyección a través del constructor (recomendada)
        @Autowired
        public MyBean(MyDependency myDependency) {
            this.myDependency = myDependency;
        }
    
        // Inyección a través de un setter (opcional)
        @Autowired
        public void setMyDependency(MyDependency myDependency) {
            this.myDependency = myDependency;
        }
    
        // Uso de la dependencia
        public void performTask() {
            myDependency.execute();
        }
    }
    
    ```
    
- **Fase de Inicialización**:
    - **Qué ocurre**: Después de que Spring ha inyectado las dependencias, el bean está casi listo para su uso. En esta fase, Spring permite ejecutar cualquier lógica de inicialización adicional que necesite el bean antes de estar completamente disponible para el resto de la aplicación.
    - **Cuándo se usa**: Se utiliza cuando necesitas configurar o preparar el bean para su uso, como abrir conexiones, cargar datos, etc.
    
    ```java
    
    @Component
    public class MyBean {
    
        @PostConstruct
        public void init() {
            System.out.println("MyBean ha sido inicializado");
            // Aquí podrías inicializar recursos como conexiones a base de datos
        }
    }
    
    ```
    
- **Fase de Uso**:
    - **Qué ocurre**: El bean está completamente inicializado y es utilizado en la aplicación. Durante esta fase, el bean participa activamente en la lógica de negocio u otras operaciones.
    - **Cuándo se usa**: Esta es la fase principal durante la cual el bean cumple su propósito dentro de la aplicación.
    
    ```java
    
    @Component
    public class MyService {
    
        @Autowired
        private MyRepository myRepository;
    
        public void performBusinessLogic() {
            // El bean está en uso, ejecutando la lógica de negocio
            myRepository.saveData("Some data");
        }
    }
    
    ```
    
- **Fase de Destrucción**:
    - **Qué ocurre**: Justo antes de que el contenedor de Spring destruya un bean (normalmente al cerrar la aplicación o liberar recursos), se pueden ejecutar métodos de limpieza.
    - **Cuándo se usa**: Es crucial para liberar recursos, cerrar conexiones o realizar otras tareas de limpieza antes de que el bean se elimine del contexto.
    
    ```java
    
    @Component
    public class MyBean {
    
        @PreDestroy
        public void destroy() {
            System.out.println("MyBean va a ser destruido");
            // Aquí podrías cerrar conexiones o liberar otros recursos
        }
    }
    
    ```
    

### 3. **Declaración de Beans**

- **Anotación `@Bean`**:
    - **Qué es**: La anotación `@Bean` se utiliza en métodos dentro de una clase anotada con `@Configuration` para declarar un bean manualmente. Esto es útil cuando necesitas mayor control sobre la creación del bean, como cuando configuras beans de bibliotecas de terceros o personalizas sus instancias.
    - **Cuándo se usa**: Cuando necesitas definir beans que no puedes anotar directamente con `@Component`, como objetos provenientes de bibliotecas externas o cuando necesitas configurar sus propiedades de manera específica.
    
    ```java
    @Configuration
    public class AppConfig {
    
        @Bean
        public DataSource dataSource() {
            DriverManagerDataSource dataSource = new DriverManagerDataSource();
            dataSource.setDriverClassName("com.mysql.cj.jdbc.Driver");
            dataSource.setUrl("jdbc:mysql://localhost:3306/mydb");
            dataSource.setUsername("user");
            dataSource.setPassword("password");
            return dataSource;
        }
    }
    
    ```
    
- **Anotación `@Component` y sus especializaciones (`@Service`, `@Repository`, `@Controller`)**:
    - **Qué es**: `@Component` es una anotación genérica que indica que una clase es un bean administrado por Spring. Las especializaciones (`@Service`, `@Repository`, `@Controller`) son anotaciones más específicas que indican el rol del bean en la arquitectura de la aplicación.
    - **Cuándo se usa**: Cuando tienes una clase que deseas que Spring maneje automáticamente, y cuando esa clase pertenece a una capa específica de la aplicación, puedes usar las especializaciones para mejorar la claridad y la semántica del código.
    
    ```java
    @Service
    public class MyService {
    
        public String greet() {
            return "Hello, Spring!";
        }
    }
    
    @Repository
    public class MyRepository {
    
        public void saveData(String data) {
            // Simulación de guardado de datos en una base de datos
            System.out.println("Data saved: " + data);
        }
    }
    
    @Controller
    public class MyController {
    
        @Autowired
        private MyService myService;
    
        @GetMapping("/greet")
        public String greet() {
            return myService.greet();
        }
    }
    ```
    

### 4. **Inyección de Dependencias**

- **Inyección a través del Constructor**:
    - **Qué es**: Es una de las formas más comunes y recomendadas de inyección de dependencias en Spring. Spring inyecta las dependencias en el constructor cuando crea una instancia del bean.
    - **Por qué es importante**: Este método asegura que el bean se construya con todas sus dependencias necesarias, promoviendo la inmutabilidad y facilitando las pruebas unitarias.
    - **Cuándo se usa**: Siempre que sea posible, especialmente cuando las dependencias son necesarias para la correcta creación y funcionamiento del bean.
    
    ```java
    @Component
    public class MyService {
    
        private final MyRepository myRepository;
    
        @Autowired
        public MyService(MyRepository myRepository) {
            this.myRepository = myRepository;
        }
    
        public void performOperation() {
            myRepository.saveData("Some Data");
        }
    }
    ```
    
- **Inyección a través de los Campos**:
    - **Qué es**: La inyección de dependencias se realiza directamente en los campos del bean. Es menos verbosa que la inyección por constructor o setter, pero tiene algunas limitaciones.
    - **Por qué es importante**: Aunque es más sencilla, no promueve la inmutabilidad y puede dificultar la realización de pruebas unitarias.
    - **Cuándo se usa**: Es útil cuando se necesita simplicidad, pero es menos preferible comparado con la inyección por constructor.
    
    ```java
    @Component
    public class MyService {
    
        @Autowired
        private MyRepository myRepository; // Inyección de dependencia en campo
    
        public void performOperation() {
            myRepository.saveData("Some Data");
        }
    }
    ```
    
- **Inyección a través de Métodos**:
    - **Qué es**: La inyección se realiza a través de métodos setters, permitiendo que Spring inyecte las dependencias después de la creación del bean.
    - **Por qué es importante**: Es útil cuando la dependencia es opcional o cuando podría cambiar después de la creación inicial del bean.
    - **Cuándo se usa**: Cuando se necesita flexibilidad para cambiar las dependencias después de la instanciación o cuando la dependencia no es obligatoria.
    
    ```java
    @Component
    public class MyService {
    
        private MyRepository myRepository;
    
        @Autowired
        public void setMyRepository(MyRepository myRepository) {
            this.myRepository = myRepository;
        }
    
        public void performOperation() {
            myRepository.saveData("Some Data");
        }
    }
    ```
    

### 8. **Creación Condicional de Beans**

- **Anotación `@Conditional`**:
    - **Qué es**: Permite la creación de beans solo si se cumplen ciertas condiciones.
    - **Por qué es importante**: Es útil para crear beans que solo deben existir bajo ciertas circunstancias, como diferentes entornos de desarrollo o producción, o ciertas configuraciones de la aplicación.
    - **Cuándo se usa**: Cuando necesitas que un bean se cree solo si se cumplen ciertos requisitos, como la existencia de un archivo de configuración, la presencia de otra clase, o un entorno específico.
    
    ```java
    @Configuration
    public class ConditionalBeansConfig {
    
        @Bean
        @Conditional(OnMissingBeanCondition.class)
        public MyService myService() {
            return new MyServiceImpl();
        }
    
        @Bean
        @ConditionalOnProperty(name = "featureX.enabled", havingValue = "true")
        public MyFeatureXService featureXService() {
            return new MyFeatureXServiceImpl();
        }
    }
    
    ```
    

### 9. **Ejemplos Prácticos**

- **Configuración Base**:
    - **Qué es**: La configuración básica con `@SpringBootApplication` inicializa el contexto de Spring Boot y escanea automáticamente los paquetes en busca de beans.
    - **Por qué es importante**: Facilita la configuración automática de la aplicación basada en las dependencias presentes, reduciendo el trabajo manual necesario.
    - **Cuándo se usa**: Siempre en aplicaciones Spring Boot como punto de entrada principal.
    
    ```java
    @SpringBootApplication
    public class MySpringBootApplication {
    
        public static void main(String[] args) {
            SpringApplication.run(MySpringBootApplication.class, args);
        }
    }
    
    ```
    
- **Inyección y Uso de Beans**:
    - **Qué es**: Demuestra cómo los beans inyectados se utilizan en una aplicación para ejecutar la lógica de negocio.
    - **Por qué es importante**: Es la base del funcionamiento de cualquier aplicación Spring, donde los beans interactúan para cumplir su propósito.
    - **Cuándo se usa**: Siempre que un bean necesita colaborar con otros beans para ejecutar tareas.
    
    ```java
    @RestController
    public class MyController {
    
        private final MyService myService;
    
        @Autowired
        public MyController(MyService myService) {
            this.myService = myService;
        }
    
        @GetMapping("/greet")
        public String greet() {
            return myService.greet();
        }
    }
    
    ```
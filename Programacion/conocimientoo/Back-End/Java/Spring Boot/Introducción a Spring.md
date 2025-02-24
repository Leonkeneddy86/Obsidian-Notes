# Introducción a Spring

## ¿ Que es Spring ?

**Spring Framework** es un marco de trabajo (framework) para el desarrollo de aplicaciones Java. Su objetivo principal es proporcionar una plataforma robusta, flexible y extensible para crear aplicaciones empresariales de manera más sencilla y eficiente.

### **Características Clave de Spring**

- **Inversión de Control (IoC)**:
    - Gestiona automáticamente los objetos (Beans) y sus dependencias.
- **Inyección de Dependencias (DI)**:
    - Proporciona un mecanismo para desacoplar las clases de sus dependencias.
- **Modularidad**:
    - Está compuesto por múltiples módulos para abordar diferentes necesidades, como:
        - **Spring Core**: IoC y DI.
        - **Spring MVC**: Desarrollo de aplicaciones web usando el patrón MVC.
        - **Spring Data**: Acceso y gestión de datos.
        - **Spring Security**: Seguridad para aplicaciones.

### **Ventajas de Spring**

- **Desarrollo más sencillo**: Simplifica tareas complejas como la gestión de transacciones o la seguridad.
- **Flexibilidad**: Puedes usar solo los módulos que necesitas.
- **Portabilidad**: Funciona en múltiples entornos (on-premise, cloud, etc.).
- **Gran comunidad y soporte**: Amplia documentación, tutoriales y extensiones.

## **¿Qué es Spring Boot?**

**Spring Boot** es un proyecto dentro del ecosistema de Spring diseñado para simplificar la creación de aplicaciones Spring. Fue introducido en 2014 para hacer que el desarrollo con Spring sea más rápido y menos complicado.

### **Características Clave de Spring Boot**

- **Autoconfiguración**:
    - Configura automáticamente los componentes del proyecto en función de las dependencias presentes.
- **Standalone Applications**:
    - Incluye un servidor embebido (como Tomcat o Jetty), eliminando la necesidad de configurar servidores externos.
- **Opinión Fuerte por Convención**:
    - Proporciona configuraciones predeterminadas que pueden ser ajustadas según sea necesario.
- **Spring Boot Starters**:
    - Paquetes predefinidos de dependencias para iniciar rápidamente proyectos específicos.
    - Ejemplo: `spring-boot-starter-web`, `spring-boot-starter-data-jpa`.
- **Spring Boot Actuator**:
    - Herramientas para monitorear y gestionar aplicaciones en tiempo de ejecución.

### **Ventajas de Spring Boot**

- **Inicio Rápido**: Genera aplicaciones listas para ejecutarse con mínimas configuraciones.
- **Menor Configuración Manual**: Configuración automática para la mayoría de los casos comunes.
- **Facilidad de Despliegue**: Ejecuta aplicaciones como un archivo JAR o WAR independiente.
- **Integración Perfecta con el Ecosistema Spring**: Todo lo que funciona en Spring también funciona en Spring Boot.

## **Diferencias entre Spring y Spring Boot**

A continuación, un cuadro comparativo para entender las diferencias clave entre ambos:

| **Aspecto** | **Spring Framework** | **Spring Boot** |
| --- | --- | --- |
| **Propósito** | Framework general para el desarrollo de aplicaciones Java. | Herramienta para simplificar la creación de aplicaciones Spring. |
| **Configuración** | Requiere configuración manual (XML, Java, o anotaciones). | Configuración automática basada en las dependencias. |
| **Servidor de Aplicaciones** | Necesitas configurarlo externamente (por ejemplo, Tomcat). | Incluye servidores embebidos como Tomcat o Jetty. |
| **Inicio del Proyecto** | Puede ser complejo y lento al definir dependencias y configuración inicial. | Usa **Spring Initializr** para generar proyectos en segundos. |
| **Dependencias** | Se gestionan manualmente; el desarrollador debe incluir cada dependencia necesaria. | Usa **starters** para agrupar dependencias comunes. |
| **Despliegue** | Generalmente requiere un WAR desplegado en un servidor externo. | Genera aplicaciones independientes que se ejecutan como archivos JAR. |
| **Actuadores** | Necesitas configurarlos manualmente si son necesarios. | Incluye **Actuator** para monitoreo y métricas por defecto. |
| **Audiencia Principal** | Desarrolladores avanzados que necesitan flexibilidad total. | Desarrolladores que buscan rapidez y simplicidad sin sacrificar funcionalidad. |

---

## **Ejemplo Comparativo**

### **Proyecto Usando Spring Framework (Tradicional)**

- **Pasos Necesarios**:
    1. Configuración de un servidor externo (Tomcat, Jetty, etc.).
    2. Configuración XML o Java para el contenedor IoC y los beans.
    3. Configuración manual de dependencias en el archivo `pom.xml` (Maven) o `build.gradle` (Gradle).

```xml

<!-- Dependencia de Spring Core -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-core</artifactId>
    <version>5.3.30</version>
</dependency>

<!-- Dependencia de Spring MVC -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>5.3.30</version>
</dependency>

```

- **Configuración XML** (para un Bean):

```xml
xml
Copy code
<beans>
    <bean id="miServicio" class="com.ejemplo.MiServicio"/>
</beans>

```

- **Controlador en Spring MVC**:

```java
java
Copy code
@Controller
public class MiControlador {

    @RequestMapping("/saludo")
    public String saludar() {
        return "Hola desde Spring Framework";
    }
}

```

---

### **Proyecto Usando Spring Boot**

- **Pasos Necesarios**:
    1. Generar el proyecto en **Spring Initializr** ([start.spring.io](https://start.spring.io/)).
    2. Incluir el starter correspondiente (por ejemplo, `spring-boot-starter-web`).
    3. Iniciar la aplicación con la anotación `@SpringBootApplication`.
- **Archivo `pom.xml` (Maven)**:

```xml
xml
Copy code
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
    <version>3.3.0</version>
</dependency>

```

- **Clase Principal**:

```java
java
Copy code
@SpringBootApplication
public class MiAplicacion {
    public static void main(String[] args) {
        SpringApplication.run(MiAplicacion.class, args);
    }
}

```

- **Controlador**:

```java
java
Copy code
@RestController
public class MiControlador {

    @GetMapping("/saludo")
    public String saludar() {
        return "Hola desde Spring Boot";
    }
}

```

- **Inicia la Aplicación**:
    - Ejecuta el comando `mvn spring-boot:run` y accede al endpoint `http://localhost:8080/saludo`.

---

## **Conclusión**

- **Spring Framework** es ideal si necesitas una solución extremadamente flexible y personalizada.
- **Spring Boot** es perfecto para comenzar rápidamente y para la mayoría de los casos de uso estándar.
- Ambos son complementarios, ya que Spring Boot está construido sobre el framework Spring y aprovecha sus capacidades.
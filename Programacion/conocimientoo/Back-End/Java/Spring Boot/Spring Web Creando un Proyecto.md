# Spring Web: Creando un Proyecto.

- Content

## **1. Crear el Proyecto con Spring Initializr**

Utilizaremos **Spring Initializr** para generar la estructura básica del proyecto.

### **Pasos:**

1. **Accede a Spring Initializr**: [https://start.spring.io/](https://start.spring.io/)
2. **Configura el Proyecto**:
    - **Project**: Maven Project
    - **Language**: Java
    - **Spring Boot**: 3.3.x (elige la versión estable más reciente dentro de la serie 3.3)
    - **Project Metadata**:
        - **Group**: `com.ejemplo`
        - **Artifact**: `demo`
        - **Name**: `demo`
        - **Package Name**: `com.ejemplo.demo`
        - **Packaging**: Jar
        - **Java**: 21
3. **Añadir Dependencias**:
    - **Spring Web**: Para crear una API REST.
    - **Spring Boot DevTools**: Para facilitar el desarrollo con recarga automática.
    - **Spring Data JPA**: Para interactuar con bases de datos mediante JPA.
    - **MySQL Driver**: Para conectar la aplicación a una base de datos MySQL.
4. **Genera el Proyecto**:
    - Haz clic en **"Generate"** para descargar el archivo ZIP del proyecto.
5. **Importa el Proyecto en tu IDE**:
    - Descomprime el archivo ZIP.
    - Abre tu IDE preferido (IntelliJ IDEA, Eclipse, Spring Tool Suite, etc.).

---

## **2. Configurar el Archivo `pom.xml`**

Asegúrate de que tu archivo `pom.xml` contenga las dependencias necesarias para una API REST con Spring Boot.

### **Contenido Básico de `pom.xml`:**

***no exacto***

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.4.0</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.example</groupId>
	<artifactId>demo</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>demo</name>
	<description>Demo project for Spring Boot</description>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>21</java.version>
	</properties>
	<dependencies>
	
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
			<scope>runtime</scope>
			<optional>true</optional>
		</dependency>
		
		<dependency>
			<groupId>com.mysql</groupId>
			<artifactId>mysql-connector-j</artifactId>
			<scope>runtime</scope>
		</dependency>
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
         
```

---

## **3. Estructura Básica del Proyecto**

Después de importar el proyecto, la estructura debería verse así:

```css
demo
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.ejemplo.demo
│   │   │       ├── DemoApplication.java
│   │   │       └── model
│   │   │           └── User.java
│   │   │       └── controller
│   │   │           └── UserController.java
│   │   │       └── service
│   │   │           └── UserService.java
│   │   │       └── repository
│   │   │           └── UserRepository.java
│   │   └── resources
│   │       └── application.properties
├── pom.xml
```

### **Componentes Clave:**

- **`DemoApplication.java`**: Clase principal que inicia la aplicación Spring Boot.
- **`model/User.java`**: Clase que representa el modelo de datos "Usuario”.
- **`controller/UserController.java`**: Controller que manejará las solicitudes HTTP relacionadas con "Usuario".
- **`service/UserService.java`**: Servicio que contiene la lógica de negocio relacionada con "Usuario”.
- **`repository/UserRepository.java`**: Se conecta con la base de datos relacionada con "Usuario”.
- **`application.properties`**: Archivo de configuración de la aplicación (con propiedades como conexión a base de datos, puerto, etc.).
# Introducción a Java y la JVM

Java es un lenguaje de programación de propósito general, orientado a objetos, desarrollado por Sun Microsystems (ahora parte de Oracle). Es ampliamente utilizado debido a su portabilidad y seguridad. Uno de los principales beneficios de Java es que el mismo código puede ejecutarse en cualquier dispositivo que tenga una Máquina Virtual de Java (JVM) instalada, siguiendo el principio "Write Once, Run Anywhere" (Escribe una vez, ejecuta en cualquier lugar).

### **Conceptos Básicos de Java**

1. **Orientación a Objetos**: Java es un lenguaje orientado a objetos, lo que significa que se basa en la utilización de objetos y clases. Los cuatro pilares de la programación orientada a objetos en Java son:
    - **Encapsulamiento**: Agrupar datos (variables) y métodos que operan sobre esos datos en una sola unidad, llamada clase.
    - **Herencia**: Crear nuevas clases basadas en clases existentes.
    - **Polimorfismo**: Permitir que una sola interfaz sea utilizada para diferentes tipos de objetos.
    - **Abstracción**: Esconder los detalles de implementación y mostrar solo la funcionalidad al usuario.
2. **Sintaxis**: La sintaxis de Java es similar a la de C y C++, lo que facilita su aprendizaje para los programadores que ya conocen estos lenguajes.

### **La Máquina Virtual de Java (JVM)**

La JVM es una parte crucial del entorno de ejecución de Java. Es una máquina abstracta que permite que los programas Java se ejecuten en cualquier dispositivo o sistema operativo. La JVM realiza varias funciones importantes:

1. **Compilación**: El código fuente de Java (archivo .java) se compila en bytecode (archivo .class) usando el compilador de Java (javac). Este bytecode es un código intermedio independiente de la plataforma.
2. **Interpretación y Ejecución**: La JVM interpreta el bytecode y lo convierte en código máquina específico de la plataforma en tiempo de ejecución. Esto permite que el mismo bytecode se ejecute en cualquier sistema operativo con una JVM compatible.
3. **Recolección de Basura (Garbage Collection)**: La JVM gestiona la memoria automáticamente, liberando memoria que ya no es utilizada por el programa mediante un proceso llamado recolección de basura.
4. **Gestión de Seguridad**: La JVM proporciona un entorno seguro para la ejecución de aplicaciones mediante un sistema de gestión de seguridad que incluye la verificación de bytecode y la gestión de permisos.

### **Proceso de Compilación y Ejecución**

1. **Escritura del Código Fuente**: El programador escribe el código en un archivo con extensión .java.
2. **Compilación**: El compilador de Java (javac) convierte el código fuente en bytecode. El comando para compilar un archivo Java es:
    
    ```bash
    javac NombreDelArchivo.java
    ```
    
    Esto genera un archivo .class que contiene el bytecode.
    

​

1. **Ejecución**: El bytecode se ejecuta en la JVM. El comando para ejecutar un archivo .class es:
    
    ```bash
    java NombreDelArchivo
    ```
    

### **Ejemplo Práctico**

**Código Fuente (HolaMundo.java)**:

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, Mundo!");
    }
}
```

​

**Compilación**:

```java
javac HolaMundo.java
```

**Ejecución**:

```java
java HolaMundo
```
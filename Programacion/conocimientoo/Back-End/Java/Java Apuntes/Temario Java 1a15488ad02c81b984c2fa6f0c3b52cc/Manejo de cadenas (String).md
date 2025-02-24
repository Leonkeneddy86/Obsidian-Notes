# Manejo de cadenas (String)

### 1. Introducción a las Cadenas en Java

Las cadenas (strings) en Java son secuencias de caracteres. La clase `String` en Java es una de las clases más utilizadas y proporciona una amplia variedad de métodos para manipular y trabajar con cadenas.

### 2. Creación y Inicialización de Cadenas

### 2.1 Declaración e Inicialización

Las cadenas en Java se pueden declarar e inicializar de varias maneras.

**Ejemplo:**

```java
String saludo = "Hola, Mundo";
String nombre = new String("Juan");
```

### 2.2 Longitud de una Cadena

El método `length()` devuelve la longitud de la cadena.

**Ejemplo:**

```java
String texto = "Java";
int longitud = texto.length();
System.out.println("Longitud: " + longitud); // Imprime: Longitud: 4
```

### 3. Concatenación de Cadenas

La concatenación de cadenas se puede realizar utilizando el operador `+` o el método `concat()`.

**Ejemplo:**

```java
String nombre = "Juan";
String apellido = "Perez";

// Usando el operador +
String nombreCompleto = nombre + " " + apellido;
System.out.println("Nombre completo: " + nombreCompleto); // Imprime: Nombre completo: Juan Perez

// Usando el método concat()
String nombreCompleto2 = nombre.concat(" ").concat(apellido);
System.out.println("Nombre completo: " + nombreCompleto2); // Imprime: Nombre completo: Juan Perez
```

### 4. Comparación de Cadenas

Para comparar cadenas en Java, se utilizan los métodos `equals()`, `equalsIgnoreCase()`, `compareTo()`, y `compareToIgnoreCase()`.

**Ejemplo:**

```java
String cadena1 = "Java";
String cadena2 = "java";

// Usando equals()
boolean sonIguales = cadena1.equals(cadena2);
System.out.println("Son iguales: " + sonIguales); // Imprime: Son iguales: false

// Usando equalsIgnoreCase()
boolean sonIgualesIgnoreCase = cadena1.equalsIgnoreCase(cadena2);
System.out.println("Son iguales (ignorando mayúsculas/minúsculas): " + sonIgualesIgnoreCase); // Imprime: Son iguales (ignorando mayúsculas/minúsculas): true

// Usando compareTo()
int comparacion = cadena1.compareTo(cadena2);
System.out.println("Comparación: " + comparacion); // Imprime un valor negativo porque "Java" es menor que "java"

// Usando compareToIgnoreCase()
int comparacionIgnoreCase = cadena1.compareToIgnoreCase(cadena2);
System.out.println("Comparación (ignorando mayúsculas/minúsculas): " + comparacionIgnoreCase); // Imprime: Comparación (ignorando mayúsculas/minúsculas): 0
```

### 5. Subcadenas

El método `substring()` se utiliza para extraer subcadenas de una cadena.

**Ejemplo:**

```java
String texto = "Hola, Mundo";

// Subcadena desde el índice 0 hasta el 4 (exclusivo)
String subcadena1 = texto.substring(0, 4);
System.out.println("Subcadena 1: " + subcadena1); // Imprime: Subcadena 1: Hola

// Subcadena desde el índice 6 hasta el final
String subcadena2 = texto.substring(6);
System.out.println("Subcadena 2: " + subcadena2); // Imprime: Subcadena 2: Mundo
```

### 6. Métodos Comunes de la Clase String

### 6.1 `charAt()`

Devuelve el carácter en una posición específica.

**Ejemplo:**

```java
String texto = "Java";
char caracter = texto.charAt(2);
System.out.println("Carácter en la posición 2: " + caracter); // Imprime: Carácter en la posición 2: v
```

### 6.2 `toUpperCase()` y `toLowerCase()`

Convierte la cadena a mayúsculas o minúsculas.

**Ejemplo:**

```java
String texto = "Java";

String textoMayusculas = texto.toUpperCase();
System.out.println("Mayúsculas: " + textoMayusculas); // Imprime: Mayúsculas: JAVA

String textoMinusculas = texto.toLowerCase();
System.out.println("Minúsculas: " + textoMinusculas); // Imprime: Minúsculas: java
```

### 6.3 `trim()`

Elimina los espacios en blanco iniciales y finales de la cadena.

**Ejemplo:**

```java
String texto = "   Java   ";
String textoSinEspacios = texto.trim();
System.out.println("Texto sin espacios: '" + textoSinEspacios + "'"); // Imprime: Texto sin espacios: 'Java'
```

### 6.4 `replace()`

Reemplaza todas las ocurrencias de un carácter o secuencia de caracteres por otra.

**Ejemplo:**

```java
String texto = "Hola, Mundo";
String textoReemplazado = texto.replace("Mundo", "Java");
System.out.println("Texto reemplazado: " + textoReemplazado); // Imprime: Texto reemplazado: Hola, Java
```

### 6.5 `split()`

Divide la cadena en un array de cadenas basado en un delimitador.

**Ejemplo:**

```java
String texto = "Java,Python,C++,JavaScript";
String[] lenguajes = texto.split(",");

for (String lenguaje : lenguajes) {
    System.out.println("Lenguaje: " + lenguaje);
}
// Imprime:
// Lenguaje: Java
// Lenguaje: Python
// Lenguaje: C++
// Lenguaje: JavaScript
```

### 7. Formateo de Cadenas

Java proporciona la clase `String.format()` para formatear cadenas.

**Ejemplo:**

```java
String nombre = "Juan";
int edad = 30;

String mensaje = String.format("Mi nombre es %s y tengo %d años", nombre, edad);
System.out.println(mensaje); // Imprime: Mi nombre es Juan y tengo 30 años
```

### 8. Bloques de Texto (Text Blocks)

Los bloques de texto (`Text Blocks`) son una característica introducida para mejorar la legibilidad y facilidad de manejo de cadenas multilínea. Permiten definir cadenas de texto que ocupan múltiples líneas de manera más conveniente.

### 8.1 Creación de Bloques de Texto

Un bloque de texto se define utilizando tres comillas dobles `"""`.

**Ejemplo:**

```java
public class TextBlocks {
    public static void main(String[] args) {
        String texto = """
                Esta es una cadena
                que ocupa varias líneas
                de texto.
                """;
        System.out.println(texto);
    }
}
```

### 8.2 Ventajas de los Bloques de Texto

- **Legibilidad:** Los bloques de texto permiten escribir cadenas multilínea de forma más legible.
- **Formato Natural:** Se mantienen los saltos de línea y los espacios en blanco como están escritos.
- **Simplicidad:** No es necesario concatenar múltiples cadenas ni utilizar caracteres de escape para saltos de línea.

**Ejemplo Avanzado:**

```java
public class TextBlocksAvanzado {
    public static void main(String[] args) {
        String json = """
                {
                    "nombre": "Juan",
                    "edad": 30,
                    "lenguajes": ["Java", "Python", "JavaScript"]
                }
                """;
        System.out.println(json);

        String sql = """
                SELECT *
                FROM usuarios
                WHERE edad > 25
                ORDER BY nombre;
                """;
        System.out.println(sql);
    }
}
```

### 9. Ejemplos Completos

### Ejemplo 1: Manipulación de Cadenas

```java
public class ManipulacionCadenas {
    public static void main(String[] args) {
        String saludo = "Hola, ";
        String nombre = "Juan";

        // Concatenación
        String mensaje = saludo + nombre;
        System.out.println("Mensaje: " + mensaje);

        // Longitud
        System.out.println("Longitud: " + mensaje.length());

        // Comparación
        String otroNombre = "juan";
        System.out.println("¿Son iguales?: " + nombre.equalsIgnoreCase(otroNombre));

        // Subcadena
        String subcadena = mensaje.substring(0, 4);
        System.out.println("Subcadena: " + subcadena);

        // Reemplazo
        String reemplazo = mensaje.replace("Juan", "Mundo");
        System.out.println("Reemplazo: " + reemplazo);

        // Mayúsculas y Minúsculas
        System.out.println("Mayúsculas: " + mensaje.toUpperCase());
        System.out.println("Minúsculas: " + mensaje.toLowerCase());

        // Dividir
        String lenguajes = "Java,Python,C++,JavaScript";
        String[] listaLenguajes = lenguajes.split(",");
        for (String lenguaje : listaLenguajes) {
            System.out.println("Lenguaje: " + lenguaje);
        }
    }
}
```

### Ejemplo 2: Entrada y Formateo de Cadenas

```java
import java.util.Scanner;

public class EntradaFormateoCadenas {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Ingrese su nombre:");
        String nombre = scanner.nextLine();

        System.out.println("Ingrese su edad:");
        int edad = scanner.nextInt();

        String mensaje = String.format("Mi nombre es %s y tengo %d años", nombre, edad);
        System.out.println(mensaje);

        scanner.close();
    }
}
```

### Resumen

1. **Declaración e inicialización de cadenas.**
2. **Métodos comunes:** `length()`, `concat()`, `equals()`, `compareTo()`, `substring()`, `charAt()`, `toUpperCase()`, `toLowerCase()`, `trim()`, `replace()`, `split()`.
3. **Formateo de cadenas** con `String.format()`.
4. **Bloques de Texto (Text Blocks):** Una forma moderna y legible de manejar cadenas multilínea.
5. **Ejemplos prácticos** que ilustran el manejo de cadenas.
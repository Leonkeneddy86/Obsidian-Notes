# La Clase Scanner en Java

## **Introducción a la Clase `Scanner`**

La clase `Scanner` es una clase en Java que se utiliza para leer **entrada de datos** de diversas fuentes, como el teclado (entrada estándar), archivos, cadenas de texto, entre otros. Forma parte del paquete `java.util` y proporciona métodos sencillos para leer y parsear diferentes tipos de datos primitivos y cadenas.

---

## **Importación de la Clase `Scanner`**

Antes de utilizar la clase `Scanner`, es necesario importarla en tu programa Java:

```java
import java.util.Scanner;
```

---

## **Creación de un Objeto `Scanner`**

Para leer datos desde una fuente específica, debes crear una instancia de `Scanner` pasando la fuente de datos al constructor.

### **1. Lectura desde el Teclado (Entrada Estándar)**

```java
Scanner scanner = new Scanner(System.in);
```

### **2. Lectura desde un Archivo**

```java
File archivo = new File("ruta/del/archivo.txt");
Scanner scanner = new Scanner(archivo);
```

### **3. Lectura desde una Cadena de Texto**

```java
String texto = "Ejemplo de texto";
Scanner scanner = new Scanner(texto);
```

---

## **Métodos Comunes de la Clase `Scanner`**

La clase `Scanner` proporciona métodos para leer diferentes tipos de datos. Los más comunes son:

### **1. Lectura de Cadenas**

- **`next()`**: Lee la siguiente palabra (delimitada por espacios en blanco).
- **`nextLine()`**: Lee toda la línea hasta el salto de línea.

**Ejemplo:**

```java
String palabra = scanner.next();      // Lee una palabra
String lineaCompleta = scanner.nextLine(); // Lee la línea completa
```

### **2. Lectura de Números**

- **`nextInt()`**: Lee un entero (`int`).
- **`nextDouble()`**: Lee un número de punto flotante de doble precisión (`double`).
- **`nextFloat()`**: Lee un número de punto flotante de precisión simple (`float`).
- **`nextLong()`**: Lee un entero largo (`long`).
- **`nextShort()`**: Lee un entero corto (`short`).
- **`nextByte()`**: Lee un byte (`byte`).

**Ejemplo:**

```java
int numeroEntero = scanner.nextInt();
double numeroDouble = scanner.nextDouble();
```

### **3. Lectura de Booleanos**

- **`nextBoolean()`**: Lee un valor booleano (`true` o `false`).

**Ejemplo:**

```java
boolean respuesta = scanner.nextBoolean();
```

### **4. Comprobación de Disponibilidad de Datos**

- **`hasNext()`**: Verifica si hay otra entrada.
- **`hasNextInt()`**, **`hasNextDouble()`**, etc.: Verifica si el siguiente token es del tipo especificado.

**Ejemplo:**

```java
if (scanner.hasNextInt()) {
    int numero = scanner.nextInt();
}
```

---

## **Ejemplos Prácticos**

### **1. Lectura de Datos desde el Teclado**

```java
import java.util.Scanner;

public class EjemploScanner {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese su nombre: ");
        String nombre = scanner.nextLine();

        System.out.print("Ingrese su edad: ");
        int edad = scanner.nextInt();

        System.out.println("Hola " + nombre + ", tienes " + edad + " años.");

        scanner.close();
    }
}
```

### **2. Lectura de Datos Numéricos con Validación**

```java
import java.util.Scanner;

public class SumaNumeros {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese el primer número: ");
        while (!scanner.hasNextDouble()) {
            System.out.println("Entrada inválida. Por favor, ingrese un número.");
            scanner.next(); // Descartar la entrada no válida
        }
        double num1 = scanner.nextDouble();

        System.out.print("Ingrese el segundo número: ");
        while (!scanner.hasNextDouble()) {
            System.out.println("Entrada inválida. Por favor, ingrese un número.");
            scanner.next();
        }
        double num2 = scanner.nextDouble();

        double suma = num1 + num2;
        System.out.println("La suma es: " + suma);

        scanner.close();
    }
}
```

---

## **Consideraciones Importantes**

### **1. Uso de `nextLine()` después de otros Métodos de Lectura**

Existe un comportamiento particular al usar `nextLine()` después de métodos como `nextInt()` o `nextDouble()`. Estos métodos no consumen el salto de línea al final de la entrada, lo que puede causar que `nextLine()` lea una línea vacía.

**Ejemplo del Problema:**

```java
System.out.print("Ingrese su edad: ");
int edad = scanner.nextInt();

System.out.print("Ingrese su nombre: ");
String nombre = scanner.nextLine(); // Puede leer una cadena vacía
```

**Solución:**

Agregar un `scanner.nextLine()` adicional después de `nextInt()` para consumir el salto de línea pendiente.

```java
System.out.print("Ingrese su edad: ");
int edad = scanner.nextInt();
scanner.nextLine(); // Consumir el salto de línea

System.out.print("Ingrese su nombre: ");
String nombre = scanner.nextLine();
```

### **2. Cierre del Objeto `Scanner`**

Es importante cerrar el objeto `Scanner` después de su uso para liberar recursos.

```java
scanner.close();
```

### **3. Manejo de Excepciones**

Los métodos de `Scanner` pueden lanzar excepciones como `InputMismatchException` si la entrada no coincide con el tipo esperado.

**Ejemplo de Manejo de Excepción:**

```jsx
import java.util.InputMismatchException;

try {
    int numero = scanner.nextInt();
} catch (InputMismatchException e) {
    System.out.println("Error: Entrada no válida. Por favor, ingrese un número entero.");
}
```
# Programación básica en Java (variables, tipos de datos, operadores)

### 1. Conceptos Básicos de Programación

### 1.1 Variables

Una variable es un espacio en la memoria de la computadora donde se almacena un valor. Cada variable tiene un nombre y un tipo de datos que define qué tipo de valor puede almacenar.

**Declaración de Variables:**

```java
int edad; // Declaración de una variable de tipo entero llamada edad
```

**Inicialización de Variables:**

```java
edad = 25; // Inicialización de la variable edad con el valor 25
```

También podemos declarar e inicializar una variable en una sola línea:

```java
int edad = 25;
```

**Ejemplo:**

```java
public class EjemploVariables {
    public static void main(String[] args) {
        int edad = 25;
        double altura = 1.75;
        String nombre = "Juan";

        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad);
        System.out.println("Altura: " + altura);
    }
}
```

### 1.2 Tipos de Datos

Los tipos de datos en Java especifican el tamaño y tipo de valores que pueden ser almacenados en una variable. Los tipos de datos se dividen en dos categorías principales: tipos primitivos y tipos de referencia.

**Tipos Primitivos:**

1. **Enteros:**
    - `byte`: 8 bits, rango de -128 a 127.
    - `short`: 16 bits, rango de -32,768 a 32,767.
    - `int`: 32 bits, rango de -2^31 a 2^31-1.
    - `long`: 64 bits, rango de -2^63 a 2^63-1.
    
    ```java
    int numero = 100;
    ```
    
2. **Punto Flotante:**
    - `float`: 32 bits, precisión simple.
    - `double`: 64 bits, precisión doble.
    
    ```java
    double precio = 19.99;
    ```
    
3. **Caracter:**
- `char`: 16 bits, un solo carácter Unicode.

```java
char letra = 'A';
```

1. **Booleano:**
- `boolean`: true o false.

```java
boolean esJavaDivertido = true;
```

**Tipos de Referencia:**

Incluyen objetos, arreglos y otros tipos de datos complejos. El más común es `String` para cadenas de texto.

```java
String saludo = "Hola, Mundo";
```

### 1.3 Operadores

Los operadores son símbolos que realizan operaciones sobre una o más operandos (variables y valores). Los principales operadores en Java incluyen:

**Operadores Aritméticos:**

- `+` (suma)
- `-` (resta)
- `*` (multiplicación)
- `/` (división)
- `%` (módulo)

**Ejemplo:**

```java
int a = 10;
int b = 5;

int suma = a + b;       // 15
int resta = a - b;      // 5
int multiplicacion = a * b; // 50
int division = a / b;   // 2
int modulo = a % b;     // 0
```

**Operadores de Asignación:**

- `=` (asignación)
- `+=` (asignación con suma)
- `-=` (asignación con resta)
- `*=`(asignación con multiplicación)
- `/=` (asignación con división)
- `%=` (asignación con módulo)

**Ejemplo:**

```java
int c = 10;
c += 5; // c ahora es 15
c -= 3; // c ahora es 12
```

**Operadores de Comparación:**

- `==` (igual a)
- `!=` (diferente de)
- `>` (mayor que)
- `<` (menor que)
- `>=` (mayor o igual que)
- `<=` (menor o igual que)

**Ejemplo:**

```java
int x = 10;
int y = 5;

boolean esIgual = (x == y); // false
boolean esMayor = (x > y);  // true
```

**Operadores Lógicos:**

- `&&` (AND lógico)
- `||` (OR lógico)
- `!` (NOT lógico)

**Ejemplo:**

```java
boolean condicion1 = true;
boolean condicion2 = false;

boolean resultadoAND = condicion1 && condicion2; // false
boolean resultadoOR = condicion1 || condicion2;  // true
boolean resultadoNOT = !condicion1;              // false
```

---

### Resumen

1. **Variables:** Espacios en memoria para almacenar datos. Se declaran y se inicializan.
2. **Tipos de Datos:**
    - Primitivos: enteros, punto flotante, caracteres y booleanos.
    - Referencia: objetos y arreglos.
3. **Operadores:**
    - Aritméticos: +, -, *, /, %.
    - Asignación: =, +=, -=, *=, /=, %=.
    - Comparación: ==, !=, >, <, >=, <=.
    - Lógicos: &&, ||, !.

### Ejercicio Práctico

Escribe un programa en Java que declare variables de diferentes tipos de datos, realice operaciones aritméticas y lógicas, y muestre los resultados.

```java
public class Practica {
    public static void main(String[] args) {
        // Declaración y inicialización de variables
        int num1 = 10;
        int num2 = 20;
        double num3 = 15.5;
        boolean esVerdadero = true;
        char letra = 'J';
        String texto = "Hola, Java";

        // Operaciones aritméticas
        int suma = num1 + num2;
        double division = num2 / num3;

        // Operaciones lógicas
        boolean resultadoLogico = (num1 < num2) && esVerdadero;

        // Mostrar resultados
        System.out.println("Suma: " + suma);
        System.out.println("División: " + division);
        System.out.println("Resultado Lógico: " + resultadoLogico);
        System.out.println("Letra: " + letra);
        System.out.println("Texto: " + texto);
    }
}
```
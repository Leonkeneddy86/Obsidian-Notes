# Métodos

### 1. Introducción a Métodos y Funciones

En Java, los términos "método" y "función" se utilizan a menudo de manera intercambiable, aunque técnicamente, las funciones son métodos que devuelven un valor y los procedimientos son métodos que no lo hacen. 

Los métodos son bloques de código que realizan una tarea específica y pueden ser llamados desde otras partes del programa para evitar la repetición de código y mejorar la organización.

### 2. Definición de Métodos

Un método se define dentro de una clase y tiene una `firma` que incluye su nombre, tipo de retorno, y parámetros (si los hay).

**Sintaxis Básica:**

```java
public class MiClase {
    // Método sin parámetros y sin retorno
    void metodoSimple() {
        // Código del método
    }

    // Método con parámetros y con retorno
    int sumar(int a, int b) {
        return a + b;
    }
}
```

### 3. Tipos de Métodos

### 3.1 Métodos sin Retorno

Los métodos que no devuelven un valor tienen el tipo de retorno `void`.

**Ejemplo:**

```java
public class EjemploMetodos {
    // Método sin retorno
    void saludar() {
        System.out.println("Hola, Mundo");
    }
}
```

### 3.2 Métodos con Retorno

Los métodos que devuelven un valor especifican el tipo de retorno antes del nombre del método y utilizan la palabra clave `return` para devolver el valor.

**Ejemplo:**

```java
public class EjemploMetodos {
    // Método con retorno
    int sumar(int a, int b) {
        return a + b;
    }
}
```

### 4. Parámetros de Métodos

Los parámetros son variables que se pasan al método para proporcionar datos que este necesita. Los parámetros se especifican dentro de los paréntesis en la definición del método.

**Ejemplo:**

```java

public class EjemploMetodos {
    // Método con parámetros y con retorno
    int multiplicar(int a, int b) {
        return a * b;
    }
}

```

### 5. Sobrecarga de Métodos

La sobrecarga de métodos permite definir múltiples métodos con el mismo nombre pero diferentes firmas (diferentes tipos o números de parámetros).

**Ejemplo:**

```java
public class EjemploSobrecarga {
    // Método sumar con dos parámetros
    int sumar(int a, int b) {
        return a + b;
    }

    // Método sumar con tres parámetros
    int sumar(int a, int b, int c) {
        return a + b + c;
    }
}

```

### 6. Métodos Estáticos

Los métodos estáticos pertenecen a la clase en lugar de a instancias de la clase. Se definen utilizando la palabra clave `static` y se pueden llamar sin crear un objeto de la clase.

**Ejemplo:**

```java
public class EjemploMetodosEstaticos {
    // Método estático
    static void imprimirMensaje() {
        System.out.println("Mensaje estático");
    }

    public static void main(String[] args) {
        // Llamada al método estático
        imprimirMensaje();
    }
}

```

### 7. Métodos Recursivos

Un método recursivo es un método que se llama a sí mismo. La recursión es útil para resolver problemas que se pueden descomponer en subproblemas más pequeños del mismo tipo.

**Ejemplo: Factorial de un número**

```java
public class EjemploRecursion {
    // Método recursivo para calcular el factorial
    static int factorial(int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }

    public static void main(String[] args) {
        int numero = 5;
        int resultado = factorial(numero);
        System.out.println("El factorial de " + numero + " es: " + resultado);
    }
}

```

### Ejemplo 1: Métodos Básicos

```java

public class MetodosBasicos {
    // Método sin retorno
    void saludar() {
        System.out.println("Hola, Mundo");
    }

    // Método con retorno
    int sumar(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        MetodosBasicos ejemplo = new MetodosBasicos();

        // Llamada a método sin retorno
        ejemplo.saludar();

        // Llamada a método con retorno
        int resultado = ejemplo.sumar(5, 3);
        System.out.println("La suma es: " + resultado);
    }
}

```

### Ejemplo 2: Sobrecarga de Métodos

```java

public class SobrecargaMetodos {
    // Método sumar con dos parámetros
    int sumar(int a, int b) {
        return a + b;
    }

    // Método sumar con tres parámetros
    int sumar(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        SobrecargaMetodos ejemplo = new SobrecargaMetodos();

        int resultado1 = ejemplo.sumar(5, 3);
        int resultado2 = ejemplo.sumar(1, 2, 3);

        System.out.println("La suma de dos números es: " + resultado1);
        System.out.println("La suma de tres números es: " + resultado2);
    }
}

```

### Resumen

1. **Definición de métodos:** Métodos sin retorno y con retorno.
2. **Parámetros de métodos:** Cómo pasar datos a los métodos.
3. **Sobrecarga de métodos:** Definir múltiples métodos con el mismo nombre pero diferentes firmas.
4. **Métodos estáticos:** Métodos que pertenecen a la clase en lugar de a instancias de la clase.
5. **Métodos recursivos:** Métodos que se llaman a sí mismos.
6. **Paso de parámetros por valor:** Entender cómo se pasan los parámetros en Java.
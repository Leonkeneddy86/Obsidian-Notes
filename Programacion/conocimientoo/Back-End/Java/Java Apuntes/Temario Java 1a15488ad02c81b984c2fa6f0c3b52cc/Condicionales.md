# Condicionales

- Content

## 1. Estructuras Condicionales

### 1.1 If-Else

La estructura `if-else` permite ejecutar bloques de código basados en condiciones booleanas.

**Sintaxis Básica:**

```java
if (condicion) {
    // Código a ejecutar si la condición es verdadera
} else {
    // Código a ejecutar si la condición es falsa
}
```

**Ejemplo:**

```java
public class EjemploIfElse {
    public static void main(String[] args) {
        int numero = 10;

        if (numero > 0) {
            System.out.println("El número es positivo.");
        } else {
            System.out.println("El número es negativo o cero.");
        }
    }
}
```

### 1.2 If-Else If-Else

Permite evaluar múltiples condiciones en secuencia.

**Sintaxis Básica:**

```java
if (condicion1) {
    // Código a ejecutar si la condición1 es verdadera
} else if (condicion2) {
    // Código a ejecutar si la condición2 es verdadera
} else {
    // Código a ejecutar si ninguna condición anterior es verdadera
}
```

**Ejemplo:**

```java
public class EjemploIfElseIf {
    public static void main(String[] args) {
        int numero = 0;

        if (numero > 0) {
            System.out.println("El número es positivo.");
        } else if (numero < 0) {
            System.out.println("El número es negativo.");
        } else {
            System.out.println("El número es cero.");
        }
    }
}
```

### 1.3 Switch

La estructura `switch` permite seleccionar entre múltiples opciones basadas en el valor de una expresión.

**Sintaxis Básica:**

```java

switch (expresion) {
    case valor1:
        // Código a ejecutar si expresion == valor1
        break;
    case valor2:
        // Código a ejecutar si expresion == valor2
        break;
    // Más casos...
    default:
        // Código a ejecutar si ninguno de los casos anteriores coincide
}
```

**Ejemplo:**

```java

public class EjemploSwitch {
    public static void main(String[] args) {
        int dia = 3;

        switch (dia) {
            case 1:
                System.out.println("Lunes");
                break;
            case 2:
                System.out.println("Martes");
                break;
            case 3:
                System.out.println("Miércoles");
                break;
            // Más casos...
            default:
                System.out.println("Día inválido");
                break;
        }
    }
}
```

### Resumen

1. **Estructuras Condicionales:**
    - `if-else`: Para condiciones simples.
    - `if-else if-else`: Para múltiples condiciones.
    - `switch`: Para seleccionar entre múltiples opciones.
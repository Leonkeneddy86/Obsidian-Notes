# Bucles

- Content

## 1. Bucles

### 1.1 Bucle For

El bucle `for` permite ejecutar un bloque de código un número específico de veces.

**Sintaxis Básica:**

```java
for (inicializacion; condicion; actualizacion) {
    // Código a ejecutar en cada iteración
}
```

**Ejemplo:**

```java
public class EjemploFor {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            System.out.println("Iteración: " + i);
        }
    }
}
```

### **1.2 Bucle For-Each**

El bucle **for-each** (también conocido como **enhanced for loop**) se introdujo en Java 5 y se utiliza para iterar de manera sencilla y legible sobre elementos de arrays o colecciones. Es especialmente útil cuando no necesitas controlar el índice de la iteración y simplemente deseas acceder a cada elemento secuencialmente.

**Sintaxis Básica:**

```java
for (tipo elemento : colección) {
    // Código a ejecutar con cada elemento
}
```

- **tipo**: El tipo de los elementos dentro de la colección o array.
- **elemento**: Una variable que representa el elemento actual en cada iteración.
- **colección**: El array o colección que se va a recorrer.

**Ejemplo con Arrays:**

```java

public class EjemploForEachArray {
    public static void main(String[] args) {
        int[] numeros = {10, 20, 30, 40, 50};

        for (int num : numeros) {
            System.out.println("Número: " + num);
        }
    }
}
```

**Salida:**

```makefile
Número: 10
Número: 20
Número: 30
Número: 40
Número: 50
```

### 1.3 Bucle While

El bucle `while` permite ejecutar un bloque de código mientras una condición sea verdadera.

**Sintaxis Básica:**

```java
while (condicion) {
    // Código a ejecutar mientras la condición sea verdadera
}
```

**Ejemplo:**

```java
public class EjemploWhile {
    public static void main(String[] args) {
        int i = 0;

        while (i < 5) {
            System.out.println("Iteración: " + i);
            i++;
        }
    }
}
```

### 1.3 Bucle Do-While

El bucle `do-while` es similar al `while`, pero garantiza que el bloque de código se ejecute al menos una vez.

**Sintaxis Básica:**

```java
do {
    // Código a ejecutar
} while (condicion);

```

**Ejemplo:**

```java
public class EjemploDoWhile {
    public static void main(String[] args) {
        int i = 0;

        do {
            System.out.println("Iteración: " + i);
            i++;
        } while (i < 5);
    }
}
```

### Resumen

1. **Bucles:**
    - `for`: Para un número específico de iteraciones.
    - `while`: Para iteraciones basadas en una condición.
    - `do-while`: Similar a `while` pero se ejecuta al menos una vez.
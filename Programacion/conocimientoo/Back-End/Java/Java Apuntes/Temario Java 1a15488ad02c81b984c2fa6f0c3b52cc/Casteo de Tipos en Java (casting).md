# Casteo de Tipos en Java (casting)

## **Introducción al Casteo de Tipos**

En Java, el **casteo** o **conversión de tipos** es el proceso de convertir un valor de un tipo de datos a otro. Esto es especialmente útil cuando necesitas operar con diferentes tipos de datos o cuando trabajas con herencia y polimorfismo en programación orientada a objetos.

## **Tipos de Casteo**

### **1. Casteo Implícito (Conversión Automática)**

- Ocurre cuando Java convierte automáticamente un tipo de datos de menor precisión a uno de mayor precisión sin pérdida de información.
- **Ejemplo**:
    
    ```java
    
    int numeroEntero = 42;
    double numeroDecimal = numeroEntero; // Casteo implícito de int a double
    ```
    

### **2. Casteo Explícito (Conversión Forzada)**

- Se requiere cuando deseas convertir un tipo de datos de mayor precisión a uno de menor precisión, lo cual puede implicar pérdida de información.
- Se utiliza la sintaxis `(tipoDeseado) valor`.
- **Ejemplo**:
    
    ```java
    
    double numeroDecimal = 42.5;
    int numeroEntero = (int) numeroDecimal; // Casteo explícito de double a int
    // numeroEntero será 42
    ```
    

## **Casteo entre Tipos Primitivos**

### **Conversión Automática (Widening Conversion)**

- **De menor a mayor precisión**:
    - `byte` → `short` → `int` → `long` → `float` → `double`
- No hay pérdida de datos y Java lo hace automáticamente.

### **Conversión Forzada (Narrowing Conversion)**

- **De mayor a menor precisión**:
    - Requiere casteo explícito.
    - Puede haber pérdida de datos o precisión.
- **Ejemplo**:
    
    ```java
    long numeroGrande = 100000L;
    int numeroPequeño = (int) numeroGrande;
    ```
    

## **Casteo entre Objetos (Referencias)**

### **Upcasting (Conversión hacia arriba)**

- Convertir una subclase a su superclase.
- Es seguro y se hace implícitamente.
- **Ejemplo**:
    
    ```java
    
    class Animal { }
    class Perro extends Animal { }
    
    Perro miPerro = new Perro();
    Animal miAnimal = miPerro; // Upcasting implícito
    ```
    

### **Downcasting (Conversión hacia abajo)**

- Convertir una superclase a una subclase.
- Requiere casteo explícito y puede ser inseguro.
- Es recomendable usar `instanceof` antes de castear.
- **Ejemplo**:
    
    ```java
    Animal miAnimal = new Perro();
    
    if (miAnimal instanceof Perro) {
        Perro miPerro = (Perro) miAnimal; // Downcasting explícito
    }
    ```
    

## **Casteo entre Interfaces y Clases**

- Puedes castear un objeto a una interfaz que implementa o viceversa.
- **Ejemplo**:
    
    ```java
    
    interface Volador { void volar(); }
    class Pajaro implements Volador {
        public void volar() { /* implementación */ }
    }
    
    Volador miVolador = new Pajaro();
    Pajaro miPajaro = (Pajaro) miVolador;
    ```
    

## **Consideraciones Importantes**

- **Pérdida de Datos**: Al castear tipos de mayor precisión a menor, puedes perder datos o precisión.
- **`ClassCastException`**: Al hacer downcasting entre objetos, si el objeto no es de la clase esperada, se lanzará esta excepción.
- **Uso de `instanceof`**: Es buena práctica verificar el tipo del objeto antes de castear.

## **Ejemplos Prácticos**

### **1. Casteo de `double` a `int`**

```java

double temperaturaDecimal = 36.6;
int temperaturaEntera = (int) temperaturaDecimal; // Resultado: 36
```

### **2. Casteo en Herencia**

```java

class Vehiculo { }
class Coche extends Vehiculo { }

Vehiculo miVehiculo = new Coche(); // Upcasting
Coche miCoche = (Coche) miVehiculo; // Downcasting

```
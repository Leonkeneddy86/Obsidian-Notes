# List en Java

# La Interfaz List en Java

### **Listas en Java**

En Java, una List es una colección que permite almacenar elementos de un mismo tipo en un orden específico. Los elementos en una lista pueden ser accedidos mediante índices, y se pueden agregar, eliminar o actualizar. La interfaz más común para listas en Java es ArrayList, aunque existen otras como LinkedList.

### **1. Crear una ArrayList vacía**

Para crear una lista vacía y luego agregar elementos, usa la clase ArrayList:

Java

Copy

import java.util.ArrayList;
import java.util.List;

List<String> lista = new ArrayList<>();

​

### **2. Rellenar la lista con el método add()**

Después de crear la lista, puedes añadir elementos individualmente usando el método add().

Java

Copy

lista.add("Elemento 1");
lista.add("Elemento 2");
lista.add("Elemento 3");

​

### **3. Crear y rellenar la lista directamente**

Es posible inicializar la lista con elementos desde el principio. Existen varias maneras de hacer esto:

### **a. Usando Arrays.asList()**

Este método crea una lista de tamaño fijo (no se puede agregar ni eliminar elementos), pero es útil para inicializar rápidamente.

Java

Copy

List<String> lista = Arrays.asList("Elemento 1", "Elemento 2", "Elemento 3");

​

### **b. Usando List.of() (Java 9+)**

A partir de Java 9, se puede usar List.of() para crear una lista inmutable (no se pueden modificar sus elementos después de la creación).

Java

Copy

List<String> lista = List.of("Elemento 1", "Elemento 2", "Elemento 3");

​

### **Métodos Más Comunes de la Interfaz List**

### **1. void add(int index, E element)**

**Descripción**: Inserta el elemento especificado en la posición especificada en la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        list.add(1, "D");
        System.out.println(list); // Output: [A, D, B, C]
    }
}

​

### **2. boolean add(E element)**

**Descripción**: Añade el elemento especificado al final de la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        System.out.println(list); // Output: [A, B, C]
    }
}

​

### **3. E get(int index)**

**Descripción**: Devuelve el elemento en la posición especificada en la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        String element = list.get(1);
        System.out.println(element); // Output: B
    }
}

​

### **4. E set(int index, E element)**

**Descripción**: Reemplaza el elemento en la posición especificada con el elemento especificado.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        list.set(1, "D");
        System.out.println(list); // Output: [A, D, C]
    }
}

​

### **5. E remove(int index)**

**Descripción**: Elimina el elemento en la posición especificada en la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        list.remove(1);
        System.out.println(list); // Output: [A, C]
    }
}

​

### **6. boolean remove(Object o)**

**Descripción**: Elimina la primera aparición del elemento especificado de la lista, si está presente.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        list.remove("B");
        System.out.println(list); // Output: [A, C]
    }
}

​

### **7. int size()**

**Descripción**: Devuelve el número de elementos en la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        int size = list.size();
        System.out.println(size); // Output: 3
    }
}

​

### **8. boolean contains(Object o)**

**Descripción**: Devuelve true si la lista contiene el elemento especificado.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        boolean contains = list.contains("B");
        System.out.println(contains); // Output: true
    }
}

​

### **9. int indexOf(Object o)**

**Descripción**: Devuelve el índice de la primera aparición del elemento especificado en la lista, o -1 si la lista no contiene el elemento.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        int index = list.indexOf("B");
        System.out.println(index); // Output: 1
    }
}

​

### **10. void clear()**

**Descripción**: Elimina todos los elementos de la lista.

**Ejemplo**:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");
        list.clear();
        System.out.println(list); // Output: []
    }
}

​

### **Diagrama de Herencia de List**

Mermaid

Preview

Copy

​

### **Explicación del Diagrama**

**Collection**: Es la interfaz raíz que define el comportamiento general de todas las colecciones.

**List**: Extiende Collection y define una colección ordenada. Las implementaciones más comunes de List son ArrayList y LinkedList.

**ArrayList**: Una implementación redimensionable de una matriz que permite acceso rápido a elementos por índice.

**LinkedList**: Una lista doblemente enlazada que permite inserciones y eliminaciones rápidas.

Este diagrama muestra cómo List hereda de Collection y cómo ArrayList y LinkedList implementan la interfaz List. También se enumeran algunos de los métodos más comunes que se pueden usar con List.

### **Ejemplos Adicionales**

### **Recorrer una Lista**

Puedes recorrer una lista usando un bucle for:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");

        // Recorrer la lista
        for (String element : list) {
            System.out.println(element);
        }
        // Output:
        // A
        // B
        // C
    }
}

​

También puedes recorrer una lista usando un bucle forEach:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");

        // Recorrer la lista usando forEach
        list.forEach(element -> {
            System.out.println(element);
        });
        // Output:
        // A
        // B
        // C
    }
}

​

### **Convertir una Lista a un Array**

Puedes convertir una lista a un array usando el método toArray:

Java

Copy

import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");

        // Convertir la lista a un array
        String[] array = list.toArray(new String[0]);

        for (String element : array) {
            System.out.println(element);
        }
        // Output:
        // A
        // B
        // C
    }
}
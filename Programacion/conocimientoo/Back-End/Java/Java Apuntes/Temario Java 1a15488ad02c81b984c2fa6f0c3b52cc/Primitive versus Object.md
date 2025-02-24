# Primitive versus Object

### **Descripción Breve de Primitives, Immutable Objects y Mutable Objects en Java**

### **Primitive Types (Primitivos)**

- Son los tipos de datos más básicos en Java.
- Almacenan un único valor directamente en la variable (por ejemplo, `int`, `double`, `boolean`, etc.).
- **Ventajas**:
    - Ocupan menos memoria en comparación con los objetos.
    - No pueden ser `null` y no tienen métodos.
- Se recomienda usar tipos primitivos cuando sea posible por su eficiencia.

---

### **Immutable Objects (Objetos Inmutables)**

- Son objetos cuyo estado no puede cambiar después de ser creados. Ejemplo: `String`, `Integer`, `LocalDate`.
- **Ventajas**:
    - Su uso hace que el código sea más predecible y fácil de entender.
    - Las referencias a objetos inmutables se pueden compartir de forma segura sin riesgo de efectos colaterales.
- **Desventajas**:
    - Ocupan más memoria, ya que cualquier cambio requiere crear una nueva instancia.
    - Pueden ser `null`, lo que podría causar excepciones si no se maneja correctamente.

---

### **Mutable Objects (Objetos Mutables)**

- Son objetos cuyo estado interno puede ser modificado después de la creación. Ejemplo: `Array`, `ArrayList`, `HashMap`.
- **Ventajas**:
    - Permiten modificar el estado directamente sin necesidad de crear nuevas instancias, lo que puede ser más eficiente en ciertos casos.
- **Desventajas**:
    - Las referencias compartidas a un objeto mutable pueden generar efectos secundarios no deseados.
    - Al asignar una variable mutable a otra, ambos apuntan al mismo objeto, lo que puede llevar a errores si se modifica el estado sin precaución.

### **Resumen Comparativo**

- **Primitivos**: Simples, eficientes, ocupan menos memoria y no permiten métodos ni ser `null`.
- **Objetos Inmutables**: Más seguros y predecibles, pero menos eficientes en memoria.
- **Objetos Mutables**: Flexibles y modificables, pero requieren cuidado con referencias compartidas.

| **Category** | **Type/Class** | **Description** | **Examples** |
| --- | --- | --- | --- |
| **Primitive Types** | `int` | 32-bit signed integer. | `int age = 25;` |
|  | `long` | 64-bit signed integer. | `long population = 7500000000L;` |
|  | `double` | 64-bit floating-point number. | `double temperature = 36.5;` |
|  | `float` | 32-bit floating-point number. | `float price = 19.99f;` |
|  | `char` | Single 16-bit Unicode character. | `char grade = 'A';` |
|  | `boolean` | True or false value. | `boolean isJavaFun = true;` |
|  | `byte` | 8-bit signed integer. | `byte smallValue = 127;` |
|  | `short` | 16-bit signed integer. | `short shortValue = 32767;` |
| **Immutable Objects** | `String` | Sequence of characters, immutable. | `String name = "Alice";` |
|  | `Integer` | Wrapper for `int`, immutable. | `Integer number = 42;` |
|  | `Double` | Wrapper for `double`, immutable. | `Double pi = 3.14159;` |
|  | `BigDecimal` | Arbitrary-precision decimal, immutable. | `BigDecimal amount = new BigDecimal("12345.67");` |
|  | `BigInteger` | Arbitrary-precision integer, immutable. | `BigInteger factorial = new BigInteger("1000000");` |
|  | `LocalDate` | Represents a date without a time zone, immutable. | `LocalDate date = LocalDate.now();` |
|  | `LocalTime` | Represents a time without a date, immutable. | `LocalTime time = LocalTime.of(14, 30);` |
|  | `LocalDateTime` | Combines date and time, immutable. | `LocalDateTime timestamp = LocalDateTime.now();` |
| **Mutable Objects** | `Array` | Fixed-size collection of elements, mutable contents. | `int[] numbers = {1, 2, 3}; numbers[0] = 42;` |
|  | `ArrayList` | Dynamic list, mutable. | `ArrayList<String> names = new ArrayList<>(); names.add("Alice");` |
|  | `HashMap` | Key-value mapping, mutable. | `HashMap<String, Integer> map = new HashMap<>(); map.put("Alice", 30);` |
|  | `HashSet` | Unordered collection of unique elements, mutable. | `HashSet<Integer> set = new HashSet<>(); set.add(42);` |
|  | `LinkedList` | Doubly linked list implementation of the `List` interface, mutable. | `LinkedList<String> list = new LinkedList<>(); list.add("Alice");` |
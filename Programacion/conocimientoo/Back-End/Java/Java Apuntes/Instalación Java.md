# Instalación Java

### **Paso a Paso de Instalación**

### **Paso 1: Descarga de Java**

1. **Accede al sitio web oficial de Oracle:**
    - Abre un navegador (Chrome, Firefox o Edge).
    - Ve a la página de descargas de Java en Oracle: [Descarga Java 21](https://www.oracle.com/es/java/technologies/downloads/#jdk21-windows).
2. **Selecciona la versión correcta:**
    - En la página, busca **Java SE Development Kit 21**.
    - Asegúrate de elegir la versión para **Windows** con extensión `.exe`.
3. **Inicia la descarga:**
    - Haz clic en el botón para descargar **jdk-21_windows-x64_bin.exe** o la versión que sea compatible con tu sistema.
    - Si el navegador solicita confirmación, selecciona **Guardar archivo**.
    - Espera a que se complete la descarga (esto puede tardar unos minutos).

---

### **Paso 2: Instalación de Java**

1. **Ejecuta el instalador:**
    - Busca el archivo descargado, que suele estar en la carpeta **Descargas**.
    - Haz doble clic en `jdk-21_windows-x64_bin.exe` para abrir el instalador.
    - Si aparece una ventana solicitando permisos de administrador, selecciona **Sí** para continuar.
2. **Configura la instalación:**
    - Se abrirá la ventana del instalador de Java. Sigue las instrucciones en pantalla.
    - **Opcional**: Puedes cambiar la ubicación de instalación, aunque se recomienda dejar la ruta predeterminada (`C:\Program Files\Java\jdk-21\`).
3. **Completa la instalación:**
    - Haz clic en **Siguiente** o **Next** en cada pantalla hasta que comience la instalación.
    - Espera a que finalice la instalación.
    - **Importante**: Al terminar, toma nota de la ubicación de instalación para el próximo paso. Por defecto, es `C:\Program Files\Java\jdk-21\`.
4. **Cierra el instalador** cuando finalice.

---

### **Paso 3: Verificar la instalación**

1. **Abre el Símbolo del sistema**:
    - Presiona `Win + R`, escribe `cmd` y pulsa **Enter**.
    - Esto abrirá la ventana del Símbolo del sistema.
2. **Ejecuta el comando de verificación**:
    - Escribe el siguiente comando y pulsa **Enter**:
        
        ```
        java -version
        ```
        
    - Si la instalación fue exitosa, verás información sobre la versión de Java (debería mostrar **Java 21**).

---

### **Paso 4: Configurar la variable de entorno JAVA_HOME**

1. **Abre el menú de Variables de entorno**:
    - Haz clic derecho en **Este equipo** y selecciona **Propiedades**.
    - En la ventana de **Propiedades del sistema**, selecciona **Configuración avanzada del sistema**.
    - Haz clic en el botón **Variables de entorno…**.
2. **Crear la variable JAVA_HOME**:
    - En la sección **Variables del sistema**, selecciona **Nueva…**.
    - En **Nombre de la variable**, escribe `JAVA_HOME`.
    - En **Valor de la variable**, escribe la ruta de instalación de Java:
        
        ```
        C:\Program Files\Java\jdk-21
        ```
        
3. **Configurar la variable PATH**:
    - En la misma ventana de Variables de entorno, selecciona la variable `Path` y haz clic en **Editar…**.
    - Haz click en New y pega la dirección de la carpeta bin de la ruta de instaalción de Java:
        
        ```
        C:\Program Files\Java\jdk-21\bin
        ```
        
    - Confirma con **Aceptar** en todas las ventanas.
4. **Cierra todas las ventanas**.

---

### **Paso 5: Reinicia el ordenador**

- Es recomendable reiniciar el ordenador para aplicar todos los cambios.
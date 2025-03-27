<h1 align="center">Calculadora en Java 🧮</h1>

Esta aplicación es una **calculadora básica** desarrollada en Java, diseñada para demostrar conceptos fundamentales de programación orientada a objetos y la construcción de interfaces gráficas de usuario utilizando el framework **Swing**. El proyecto fue creado en el entorno de desarrollo **NetBeans**, lo que permitió aprovechar su editor visual para organizar y diseñar la interfaz de forma intuitiva.

### ¿Qué hace esta aplicación?

- La calculadora permite realizar las operaciones aritméticas esenciales: suma, resta, multiplicación y división.
- Los números y operadores se ingresan a través de botones con un tamaño fijo (80px x 80px), mientras que el resultado y las entradas se muestran en un área dedicada (un campo de texto de 50px de alto).
- Con un enfoque en la usabilidad, la interfaz muestra los valores y resultados de manera clara y ordenad.

### ¿Por qué es interesante este proyecto?

- Es un excelente ejemplo para comprender el manejo de eventos en aplicaciones gráficas y la interacción entre componentes visuales, consolidando así bases sólidas en Java y Swing.
- La estructura del proyecto fomenta buenas prácticas de desarrollo, manteniendo separadas la lógica de la interfaz y el procesamiento de operaciones.
- Más allá de su función como simple herramienta de cálculo, la aplicación sirve como demostración práctica en portfolios.

### ¿Qué se uso para desarrollar esta calculadora?

- **Lenguaje de programación:** Java
- **Entorno de Desarrollo (IDE):** NetBeans
- **Framework de interfaz gráfica:** Swing
  Swing fue empleado para construir la interfaz, utilizando componentes como:
  - **JFrame:** Ventana principal de la aplicación.
  - **JPanel:** Paneles para la organización de los componentes.
  - **JLabel:** Área de visualización para entradas y resultados.
  - **JButton:** Botones con dimensiones fijas (80px x 80px) para ingresar números y operaciones.
- **Librerías estándar de Java:**
  Se aprovecharon las librerías nativas de Java para el manejo de eventos y la gestión de excepciones, garantizando una experiencia de usuario fluida y segura.

---

<h2 align="center">Análisis del código</h2>

### 1. Estructura y herencia

- **Herencia de JFrame:**
  La clase `Calculadora` extiende de `javax.swing.JFrame`, lo que la convierte en una ventana de aplicación. Esto permite aprovechar los métodos y propiedades de JFrame para crear y gestionar la interfaz gráfica de usuario (GUI).
  Se utiliza `setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE)` para definir el comportamiento al cerrar la ventana.

### 2. Variables de instancia

- **Variables para Operaciones:**
  - `public float primernumero;`
  - `public float segundonumero;`
  - `public String operador;`
    Estas variables almacenan los operandos y el operador seleccionado para realizar las operaciones aritméticas.

### 3. Constructor y configuración

- **Constructor:**
  En el constructor se llama a `initComponents()`, método generado automáticamente por el editor visual de NetBeans, el cual se encarga de inicializar y disponer todos los componentes gráficos en la interfaz.
  Además, se usa `this.setLocationRelativeTo(null);` para centrar la ventana en la pantalla.
  🔍 **Nota:** El método `initComponents()` contiene el código generado automáticamente y no debe ser modificado manualmente.

### 4. Configuración de la interfaz gráfica

- **Panel y componentes:**
  - Se utiliza un `JPanel` (`jPanel1`) para agrupar los componentes.
  - **Visor (JLabel):** Se utiliza para mostrar la entrada del usuario y los resultados. Se alinea a la derecha y se le da un borde personalizado para destacarlo.
  - **Botones (JButton):**
    - Se han creado botones para cada dígito (0-9) y para los operadores (`+`, , , `/`), además de botones para la función "C" (limpiar) y "=" (calcular).
    - Cada botón tiene un tamaño fijo (80px x 80px) para mantener la consistencia del diseño.
- **Diseño y organización:**
  Se usa un `GroupLayout` para organizar los componentes tanto horizontal como verticalmente, lo que permite disponer la calculadora de forma ordenada y adaptable al tamaño de la ventana.

### 5. Manejo de eventos y funcionalidad

- **Accionadores de eventos:**
  Cada botón tiene un `ActionListener` que define la acción a realizar al hacer clic:
  - **Ingreso de números:**
    Por ejemplo, en el método `jButton1ActionPerformed`, se concatena el número "1" al texto del visor:
    ```java
    this.Visor.setText(this.Visor.getText()+"1");
    ```
  - **Operaciones aritméticas:**
    Cuando se presiona un botón de operador (como `+`), se:
    - Se parsea el número que se muestra en el visor y se almacena en `primernumero`.
    - Se asigna el operador correspondiente a la variable `operador`.
    - Se limpia el visor para permitir la entrada del segundo número.
  - **Ejecutar la operación (Botón "="):**
    En el método `jButtonIgualActionPerformed` se:
    - Se parsea el número mostrado en el visor como `segundonumero`.
    - Se utiliza una estructura `switch` para determinar qué operación realizar según el operador almacenado.
    - Se manejan posibles errores, como la división por cero, mostrando un mensaje específico en el visor.
    - Se usa el método `sincero` para convertir el resultado a cadena y, si el resultado es un número entero (sin parte decimal), se formatea para no mostrar decimales innecesarios.

### 6. Método de formateo de resultados

- **Método `sincero`:**
  Este método recibe un resultado de tipo `float` y devuelve su representación en cadena. Si el número es entero (es decir, sin decimales significativos), elimina la parte decimal.
  ```java
  public String sincero(float resultado) {
      String retorno = Float.toString(resultado);
      if (resultado % 1 == 0) {
          retorno = retorno.substring(0, retorno.length() - 2);
      }
      return retorno;
  }
  ```
  🔧 **Función:** Garantiza que los resultados se muestren de forma limpia y legible, evitando mostrar ".0" cuando no es necesario.

### 7. Método main y configuración de “look and feel”

- **Método `main`:**
  El método `main` configura el "look and feel" de la aplicación utilizando Nimbus, lo que aporta una apariencia moderna a la interfaz. Se recorre la lista de "look and feel" instalados y se aplica Nimbus si está disponible.
  Luego, se invoca el constructor de `Calculadora` dentro del hilo de eventos de Swing mediante `java.awt.EventQueue.invokeLater`, asegurando que la GUI se construya y actualice de forma segura.

---

En conclusión, el código de esta calculadora es un ejemplo clásico de cómo integrar la lógica de negocio con una interfaz gráfica en Java utilizando Swing. Cada componente, desde la disposición de los botones hasta el manejo de eventos, está cuidadosamente diseñado para ofrecer una experiencia de usuario coherente y funcional. Este proyecto no solo demuestra conocimientos en Java y GUI, sino que también destaca buenas prácticas en la estructuración del código y el uso de herramientas de desarrollo como NetBeans.

---

<p align="center">
<big><strong>✨¡Gracias por visitar este repositorio!✨</strong></big>
</p>

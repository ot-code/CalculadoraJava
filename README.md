# Calculadora en Java 🧮 (resumido)

<div align="center">
  <img src="
  " alt="Calculadora sin ejecutar" width="700" height="600" />
  <img src="
  " alt="Calculadora ejecutada" width="700" height="600" />
</div>
<div align="center">
  App ejecutada en terminal
</div>

Calculadora mostrando el resultado de la operaciónde 29+29

Este proyecto consiste en una **calculadora** desarrollada en **Java** utilizando el entorno de desarrollo **NetBeans**. La aplicación implementa las cuatro operaciones básicas: suma, resta, multiplicación y división, permitiendo la entrada de datos exclusivamente mediante **botones** en lugar de teclado, lo cual la hace ideal para interfaces táctiles o dispositivos con entrada limitada.

### Componentes y herramientas

- **Lenguaje de programación:** Java
  Se utiliza Java para implementar tanto la lógica de negocio como la interfaz gráfica, aprovechando la portabilidad y robustez del lenguaje.
- **Entorno de desarrollo:** NetBeans
  La aplicación se ha desarrollado en NetBeans, lo que facilita la creación de interfaces visuales a través de su editor gráfico.
- **Biblioteca de interfaz gráfica:** Swing
  La interfaz se ha construido usando componentes Swing, como:
  - **JFrame:** Ventana principal que contiene la aplicación.
  - **JPanel:** Panel para organizar los componentes de manera estructurada.
  - **JLabel:** Actúa como visor para mostrar los números y resultados.
  - **JButton:** Botones para los dígitos (0-9) y las operaciones (+, -, \*, /, C, =) con un tamaño fijo (80px x 80px), asegurando uniformidad en el diseño.
  - **Manejo de eventos:** Cada botón tiene un `ActionListener` para capturar la acción del usuario y realizar la operación correspondiente.

### Funcionalidad

- **Ingreso de números y operadores:**
  Los números se ingresan mediante la concatenación en el visor cada vez que se presiona un botón numérico. Los operadores se gestionan de forma que, al pulsarlos, se almacena el primer número y se limpia el campo para ingresar el segundo operando.
- **Ejecución de operaciones:**
  Al presionar el botón "=" se realiza el cálculo correspondiente basado en el operador almacenado. Se incluyen validaciones, por ejemplo, mostrando un mensaje de error cuando se intenta dividir entre cero.
- **Limpieza de datos:**
  La funcionalidad del botón "C" permite limpiar el visor y reiniciar las variables, asegurando que el usuario pueda comenzar una nueva operación sin inconvenientes.
- **Interfaz amigable:**
  La aplicación cuenta con un diseño sencillo y visualmente atractivo, facilitando la interacción incluso para usuarios sin conocimientos técnicos. Además, se han incluido detalles estéticos (como bordes y colores) para realzar la experiencia del usuario.

---

<p align="center">
<big><strong>✨¡Gracias por visitar este repositorio!✨</strong></big>
</p>

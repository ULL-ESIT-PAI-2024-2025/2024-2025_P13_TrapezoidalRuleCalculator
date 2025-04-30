# Práctica 13. Programación de Aplicaciones Interactivas. Calculadora de áreas usando la regla del trapecio.
### Factor de ponderación: 10 

### Examen de la asignatura
Tenga en cuenta que esta es la primera de las dos prácticas que componen el examen final de la asignatura.

### Objetivos
Los objetivos de esta tarea son poner en práctica:
* Integración continua para un proyecto de prácticas de la asignatura
* La arquitectura Modelo Vista Controlador
* Conceptos de Programación orientada a eventos en TypeScript.
* Conceptos de Programación Gráfica en TypeScript usando la API Canvas.
* Metodologías y conceptos de Programación Orientada a Objetos en TypeScript.
* Principios y Buenas prácticas de programación Orientada a Objetos.
* El uso del framework Bulma para dotar de estilo a una aplicación web simple.
* El uso de elementos HTML.

### Revise cuidadosamente los elementos de esta rúbrica puesto que será la que se utilice para la evaluación de la práctica

1. Tanto el ejercicio propuesto para esta práctica como los que se propondrán en la sesión de evaluación
   han de entregarse en la correspondiente tarea del aula virtual a través de un repositorio privado de
   [GitHub](https://github.com/)
1. Su proyecto ha de incluir un fichero `README.md` con indicaciones precisas para compilar (*build*) y desplegar su aplicación en una 
   [página GitHub](https://pages.github.com/)
   asociada con el repositorio del proyecto
1. Su proyecto ha de incluir un fichero de configuración del flujo de desarrollo que permita automatizar mediante 
   [GitHub Actions](https://github.com/features/actions)
   la ejecución de las diferentes tareas del proyecto
1. La aplicación debe adherirse al paradigma de programación orientada a objetos e implementarse de acuerdo con la arquitectura MVC, 
   aplicando fundamentos, principios y buenas prácticas de OOP
1. La estructura de clases de su aplicación se mostrará mediante un diagrama UML expuesto a través de una página GitHub del proyecto
1. El comportamiento de su aplicación deberá ajustarse a lo descrito en este documento
1. Los estilos de su aplicación han de implementarse utilizando el Framework
   [Bulma](https://bulma.io/)
1. Los métodos y clases de su aplicación estarán convenientemente documentados utilizando etiquetas
   [JSDoc](https://jsdoc.app/)
   y la documentación de la misma se generará utilizando
   [TypeDoc](https://typedoc.org/)
   y se alojará en una página GitHub de su proyecto
1. La aplicación ha de contener tests unitarios realizados con 
   [Jest](https://jestjs.io/)
   para alguno(s) de los métodos que se desarrollen para su aplicación
1. Mediante el uso de 
   [typescript-eslint](https://typescript-eslint.io/)
   se comprobará que el código de su aplicación se adhiere a las reglas de las Guías de Estilo de Google para 
   [TypeScript](https://google.github.io/styleguide/tsguide.html)
   y
   [JavaScript](https://google.github.io/styleguide/jsguide.html)

### Indicaciones de caracter general
* La aplicación que desarrolle ha de ser orientada a objetos y conforme a la arquitectura MVC.
Ponga en práctica en su desarrollo los fundamentos, principios y buenas prácticas de la OOP así como los
conocimientos que haya adquirido en el uso de patrones de diseño.

* Aloje ficheros de configuración adecuados en el directorio raíz de su proyecto, de modo que se contemplen todas las dependencias del mismo.

* Utilice un fichero distinto para el código de cada una de las clases que intervienen en su programa.

* Previo a la implementación de cada clase, diseñe y desarrolle un conjunto de tests para probar el correcto
 funcionamiento de todos los métodos públicos.

* Encapsule las clases en módulos que exporten la correspondiete clase hacia otros programas clientes que pudieran utilizarla.

* Todo el código estará ubicado en el directorio `src/home-work` del proyecto. Use subdirectorios de éste si le resulta conveniente.

* Antes de comenzar a desarrollar su programa dedique el tiempo necesario a diseñar la estructura de clases que 
utilizará en su programa, así como las relaciones existentes entre las mismas. 
Utilice 
[LucidChart](https://www.lucidchart.com/pages/es)
o una aplicación similar para realizar un diagrama UML para esas clases, que ha de añadir a la página índice de esta práctica. Asegúrese de la corrección de su diagrama UML.

* Realice, como siempre, un diseño incremental del programa comprobando cada una de las funcionalidades que añade, siguiendo un
desarrollo TDD.

* Cuando finalice su desarrollo **modifique el fichero `README.md`** de su proyecto incluyendo la información habitual en cualquier proyecto público en GitHub. 
Incluya en ese fichero dos apartados, Building and Running the code y Live Demo. 
En el primero de ellos ha de explicar en detalle cómo a partir de clonar su repo público ha de compilarse, ejecutarse y desplegarse su aplicación, 
mientras que en el segundo ha de incluir un enlace (véase el apartado *Presentación de resultados de este documento*) a la URL pública donde deberá estar disponible su aplicación.
Haga que el fichero `README.md` de su proyecto sea la primera página de la documentación del mismo.

Incluya en su proyecto un fichero de configuración del flujo que permita automatizar la ejecución de las
diferentes tareas del proyecto.

Incluya en su flujo de trabajo al menos las siguientes etapas:
* Análisis estático de su código utilizando ESLint. Utilice 
[typescript-eslint](https://typescript-eslint.io/)
para habilitar el análisis de código TypeScript en ESLint y configure el linter para que analice la
conformidad de su código con la Guía de Estilo de Google para TS.
* Generación de la documentación de su proyecto utilizando
[TypeDoc](https://typedoc.org/)
* Despliegue de su aplicación en una 
[GitHub Page](https://pages.github.com/) 
asociada con el repositorio de su proyecto.

### Cálculo de áreas usando la regla del trapecio 
En esta práctica se propone desarrollar una aplicación TypeScript basada en el patrón MVC.
La aplicación permitirá el cálculo aproximado del área bajo una curva utilizando la regla del trapecio y
dispondrá de una interfaz gráfica que permitirá visualizar la aplicación de la regla así como modificar
algunos parámetros del cálculo.

La 
[regla del trapecio](https://en.wikipedia.org/wiki/Trapezoidal_rule)
es un método de integración numérica, es decir, un método para calcular aproximadamente el valor de una integral definida. 
La regla se basa en aproximar el valor de la integral por la suma de las áreas de una serie de trapecios,
siendo muy fácil calcular el área de un trapecio.
Cuanto mayor es el número de trapecios, mejor será la aproximación que se consiga para el área.

[Esta aplicación](https://academo.org/demos/trapezoidal-rule-calculator/)
se tomará como referencia para la que se propone desarrollar y en ella dispone de una explicación más
detallada de la regla del trapecio.

Diseñe su aplicación web como una SPA
([Single-page application](https://en.wikipedia.org/wiki/Single-page_application))
de modo que toda la simulación se muestre en el viewport del navegador sin necesidad de usar las barras de scroll.

En su aplicación (y a diferencia de la de referencia), al pulsar el botón 'Update' el valor aproximado del área de la
curva se imprimirá (*Sum of all Trapezium areas:*) en la página en la parte inferior de la misma, por debajo
del área ocupada por el canvas.

En su aplicación necesitará evaluar una función que es introducida como texto por el usuario (Campo *Expression*).
Para ello puede resultarle útil usar
[mathjs](https://mathjs.org/)
que incluye un analizador sintáctico de expresiones.

### Interfaz gráfica del programa
La interfaz gráfica de la aplicación a diseñar imitará la de
[la aplicación de referencia](https://academo.org/demos/trapezoidal-rule-calculator/)
pero no incluirá la tabla de la parte inferior de la página que muestra el área de los diferentes trapecios.
Si lo desea, puede mostrar (a efectos de depuración) esas áreas imprimiéndolas en consola.

También el comportamiento lógico de su aplicación debe imitar a la de referencia.

Utilice libremente los elementos HTML que considere más adecuados para la interfaz gráfica de su aplicación y
dote de estilo a esos elementos utilizando Bulma para imitar la tipografía y colores de la ULL.

### Presentación de resultados
Configure una página GitHub asociada con su repositorio de trabajo que sirva de índice para estas otras
páginas de su proyecto:
* La aplicación *Integración* que habrá desarrollado. Esa aplicación se configurará como una SPA.
* La documentación de la aplicación.
* El diagrama UML de las clases utilizadas en la aplicación.
* Una página que albergará el ejercicio que se le pedirá realizar en la sesión de evaluación de esta práctica.

Todas estas páginas deberán tener un estilo personalizado que imite utilizando Bulma el aspecto (tipografía, colores) de las *páginas ULL*.

## Referencias
* [Trapezoidal Rule Calculator](https://academo.org/demos/trapezoidal-rule-calculator/)
* [GitHub Actions](https://github.com/features/actions)
* [GitHub Pages](https://pages.github.com/)
* [Bulma](https://bulma.io/)
* [TypeDoc](https://typedoc.org/)
* [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [ESLint](https://eslint.org/)
* [JSDoc](https://jsdoc.app/)
* [Jest](https://jestjs.io/)
* [PAI Code Examples](https://github.com/ULL-ESIT-PAI-2024-2025/PAI-class-code-examples)

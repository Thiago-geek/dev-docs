# Javascript
JavaScript es un tema muy amplio, con muchas características, estilos y técnicas diferentes para aprender, y muchas API y herramientas creadas sobre él. Este módulo se centra principalmente en los aspectos esenciales del lenguaje principal, además de algunos temas clave relacionados; aprender estos temas le brindará una base sólida sobre la cual trabajar.

# ¿Qué es JavaScript?
JavaScript es un lenguaje de programación que permite implementar funciones complejas en páginas web. Cada vez que una página web hace algo más que simplemente estar ahí y mostrar información estática para que la mires (mostrar actualizaciones de contenido oportunas, mapas interactivos, gráficos animados 2D/3D, jukeboxes de video con desplazamiento, etc.), puedes apostar a que probablemente JavaScript esté involucrado. Es la tercera capa de la torta de capas de las tecnologías web estándar, dos de las cuales ( HTML y CSS ) hemos cubierto con mucho más detalle en otras partes del Área de aprendizaje.

![](images.png/torta3Capaz.png)
  
* `HTML` es el lenguaje de marcado que utilizamos para estructurar y dar significado a nuestro contenido web, por ejemplo, definiendo párrafos, encabezados y tablas de datos, o incrustando imágenes y vídeos en la página.

* `CSS` es un lenguaje de reglas de estilo que usamos para aplicar estilos a nuestro contenido HTML, por ejemplo, establecer colores de fondo y fuentes, y diseñar nuestro contenido en múltiples columnas.

* `JavaScript` es un lenguaje de programación que permite crear contenido que se actualiza de forma dinámica, controlar contenido multimedia, animar imágenes y prácticamente todo lo demás. (Bueno, no todo, pero es sorprendente lo que se puede lograr con unas pocas líneas de código JavaScript).

# Entonces, ¿qué puede hacer realmente?
El lenguaje principal del cliente JavaScript consta de algunas características de programación comunes que le permiten hacer cosas como:

* Almacenar valores útiles dentro de las variables. 

* Operaciones sobre fragmentos de texto (conocidos como "cadenas" en programación).

* `click` Ejecución de código en respuesta a determinados eventos que ocurren en una página web.

* ¡Y mucho más!

Pero lo que es aún más interesante es la funcionalidad desarrollada sobre el lenguaje JavaScript del lado del cliente. Las denominadas interfaces de programación de aplicaciones ( API ) le brindan superpoderes adicionales para usar en su código JavaScript.

Las API son conjuntos de bloques de código listos para usar que permiten a un desarrollador implementar programas que de otro modo serían difíciles o imposibles de implementar. Hacen lo mismo para la programación que los kits de muebles listos para usar para la construcción de viviendas: es mucho más fácil tomar paneles ya cortados y atornillarlos para hacer una estantería que elaborar el diseño uno mismo, buscar la madera correcta, cortar todos los paneles con el tamaño y la forma adecuados, encontrar los tornillos del tamaño correcto y luego unirlos para hacer una estantería.

![imagenAPI](images.png/imageAPI.png)

Las API del navegador están integradas en el navegador web y pueden exponer datos del entorno informático circundante o realizar tareas complejas y útiles. 

# ¿Qué hace JavaScript en tu página?
Aquí comenzaremos a mirar algo de código y, mientras lo hacemos, exploraremos lo que realmente sucede cuando ejecutas JavaScript en tu página.

Recapitulemos brevemente la historia de lo que sucede cuando cargas una página web en un navegador. Cuando cargas una página web en tu navegador, estás ejecutando tu código (HTML, CSS y JavaScript) dentro de un entorno de ejecución (la pestaña del navegador). Esto es como una fábrica que toma materias primas (el código) y produce un producto (la página web).

![laWeb](images.png/laweb.png)

Un uso muy común de JavaScript es modificar dinámicamente HTML y CSS para actualizar una interfaz de usuario, a través de la API del Modelo de objetos de documento (como se mencionó anteriormente).

# Seguridad del navegador
Cada pestaña del navegador tiene su propio contenedor independiente para ejecutar código (estos contenedores se denominan "entornos de ejecución" en términos técnicos); esto significa que, en la mayoría de los casos, el código de cada pestaña se ejecuta de forma completamente independiente y el código de una pestaña no puede afectar directamente al código de otra pestaña o de otro sitio web. Esta es una buena medida de seguridad; si no fuera así, los piratas podrían empezar a escribir código para robar información de otros sitios web y otras cosas malas similares.


# Orden de ejecución de JavaScript
Cuando el navegador encuentra un bloque de JavaScript, generalmente lo ejecuta en orden, de arriba hacia abajo. Esto significa que debes tener cuidado con el orden en el que colocas las cosas. Por ejemplo, volvamos al bloque de JavaScript

```javascript
const button = document.querySelector("button");

button.addEventListener("click", updateName);

function updateName() {
  const name = prompt("Enter a new name");
  button.textContent = `Player 1: ${name}`;
}
```

Aquí, primero seleccionamos un botón con document.querySelector, luego le adjuntamos un detector de eventos con addEventListener, de modo que cuando se haga clic en el botón, updateName()se ejecute el bloque de código (líneas 5 a 8). El updateName()bloque de código (estos tipos de bloques de código reutilizables se denominan "funciones") solicita al usuario un nuevo nombre y luego inserta ese nombre en el texto del botón para actualizar la pantalla.

Si cambiaras el orden de las dos primeras líneas de código, ya no funcionaría; en su lugar, obtendrías un error en la consola para desarrolladores del navegador .

# Código interpretado versus código compilado
Es posible que hayas oído hablar de los términos "interpretado" y "compilado" en el contexto de la programación. En los lenguajes interpretados, el código se ejecuta de arriba a abajo y el resultado de la ejecución del código se devuelve inmediatamente. No tienes que transformar el código en un formato diferente antes de que el navegador lo ejecute. El código se recibe en su formato de texto fácil de usar para el programador y se procesa directamente a partir de ahí.

Por otra parte, los lenguajes compilados se transforman (compilan) en otro formato antes de que el ordenador los ejecute. Por ejemplo, C/C++ se compilan en código de máquina que luego ejecuta el ordenador. El programa se ejecuta desde un formato binario, que se generó a partir del código fuente del programa original.

JavaScript es un lenguaje de programación interpretado ligero. El navegador web recibe el código JavaScript en su forma de texto original y ejecuta el script a partir de él. Desde un punto de vista técnico, la mayoría de los intérpretes de JavaScript modernos utilizan una técnica llamada compilación en tiempo real para mejorar el rendimiento; el código fuente de JavaScript se compila en un formato binario más rápido mientras se utiliza el script, de modo que se pueda ejecutar lo más rápido posible. Sin embargo, JavaScript todavía se considera un lenguaje interpretado, ya que la compilación se realiza en tiempo de ejecución, en lugar de antes.

Ambos tipos de lenguaje tienen ventajas, pero no las analizaremos ahora.



# Código del lado del servidor versus código del lado del cliente
También es posible que escuches los términos código del lado del servidor y del lado del cliente , especialmente en el contexto del desarrollo web. El código del lado del cliente es el código que se ejecuta en la computadora del usuario: cuando se visualiza una página web, se descarga el código del lado del cliente de la página, que luego se ejecuta y se muestra en el navegador. En este módulo, hablamos explícitamente de JavaScript del lado del cliente .

Por otro lado, el código del lado del servidor se ejecuta en el servidor, luego sus resultados se descargan y se muestran en el navegador. Algunos ejemplos de lenguajes web del lado del servidor populares son PHP, Python, Ruby, C# e incluso JavaScript. JavaScript también se puede utilizar como lenguaje del lado del servidor, por ejemplo, en el popular entorno Node.js.

# Código dinámico versus código estático
La palabra dinámico se utiliza para describir tanto el lenguaje JavaScript del lado del cliente como los lenguajes del lado del servidor; se refiere a la capacidad de actualizar la visualización de una página web o aplicación para mostrar cosas diferentes en diferentes circunstancias, generando contenido nuevo según sea necesario. El código del lado del servidor genera contenido nuevo dinámicamente en el servidor, por ejemplo, extrayendo datos de una base de datos, mientras que el código JavaScript del lado del cliente genera contenido nuevo dinámicamente dentro del navegador del cliente, por ejemplo, creando una nueva tabla HTML, llenándola con los datos solicitados al servidor y luego mostrando la tabla en una página web que se muestra al usuario. El significado es ligeramente diferente en los dos contextos, pero está relacionado, y ambos enfoques (del lado del servidor y del lado del cliente) suelen funcionar juntos.

Una página web sin contenido que se actualice dinámicamente se denomina estática : simplemente muestra el mismo contenido todo el tiempo.

# ¿Cómo agregar JavaScript a tu página?
JavaScript se aplica a tu página HTML de forma similar a CSS. Mientras que CSS utiliza `<link>` elementos para aplicar hojas de estilo externas y `<style>` elementos para aplicar hojas de estilo internas a HTML, JavaScript solo necesita un amigo en el mundo de HTML: el `<script>` elemento. Veamos cómo funciona esto.

```html
<script>
  // JavaScript goes here
</script>
```

Tenga en cuenta que el código de sus documentos web generalmente se carga y se ejecuta en el orden en que aparece en la página. Al colocar el código JavaScript en la parte inferior, nos aseguramos de que se carguen todos los elementos HTML.

Ahora agregaremos algo de JavaScript dentro de nuestro `<script>` elemento para que la página haga algo más interesante

```javascript
function createParagraph() {
  const para = document.createElement("p");
  para.textContent = "You clicked the button!";
  document.body.appendChild(para);
}

const buttons = document.querySelectorAll("button");

for (const button of buttons) {
  button.addEventListener("click", createParagraph);
}
```

Guarde el archivo y actualice el navegador; ahora debería ver que cuando hace clic en el botón, se genera un nuevo párrafo y se coloca debajo.

# JavaScript externo
Esto funciona muy bien, pero ¿qué sucede si queremos poner nuestro código JavaScript en un archivo externo? Vamos a analizarlo ahora.

Primero, crea un nuevo archivo en el mismo directorio que el archivo HTML de muestra. Llámalo script.jsy asegúrate de que tenga la extensión de nombre de archivo .js, ya que así es como se reconoce como JavaScript.

Elimina el elemento actual `<script>` en la parte inferior `</body>` y agrega lo siguiente justo antes de la `</head>` etiqueta de cierre (de esa manera, el navegador puede comenzar a cargar el archivo antes que cuando está en la parte inferior):

```html
<script type="module" src="script.js"></script>
```

Dentro script.js, agrega el siguiente script:

```javascript
function createParagraph() {
  const para = document.createElement("p");
  para.textContent = "You clicked the button!";
  document.body.appendChild(para);
}

const buttons = document.querySelectorAll("button");

for (const button of buttons) {
  button.addEventListener("click", createParagraph);
}
```

# Controladores de JavaScript en línea
Ten en cuenta que, a veces, te encontrarás con fragmentos de código JavaScript dentro de HTML. Podría tener un aspecto similar al siguiente:

```javascript
function createParagraph() {
  const para = document.createElement("p");
  para.textContent = "You clicked the button!";
  document.body.appendChild(para);
}
```

```html
<button onclick="createParagraph()">Click me!</button>
```

Esta demostración tiene exactamente la misma funcionalidad que en las dos secciones anteriores, excepto que el `<button>` elemento incluye un `onclick` controlador en línea para hacer que la función se ejecute cuando se presiona el botón.

Sin embargo, no hagas esto. Es una mala práctica contaminar tu código HTML con JavaScript y es ineficiente: tendrías que incluir el `onclick="createParagraph()"` atributo en cada botón al que quieras aplicar JavaScript.


# Estrategias de carga de scripts
Todo el código HTML de una página se carga en el orden en el que aparece. Si utiliza JavaScript para manipular elementos de la página (o, más precisamente, el (Modelo de objetos del documento)[https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/DOM_scripting#the_document_object_model] ), su código no funcionará si el código JavaScript se carga y analiza antes que el código HTML al que intenta hacer algo.

Existen algunas estrategias diferentes para garantizar que su JavaScript solo se ejecute después de analizar el HTML:

* En el ejemplo interno de JavaScript anterior, el elemento de script se coloca en la parte inferior del cuerpo del documento y, por lo tanto, solo se ejecuta después de que se analiza el resto del cuerpo HTML.

* En el ejemplo de JavaScript externo anterior, el elemento script se coloca en el encabezado del documento, antes de que se analice el cuerpo HTML.Pero como estamos usando `<script type="module">`, el código se trata como un módulo y el navegador espera a que se procese todo el HTML antes de ejecutar los módulos JavaScript. También puede colocar scripts externos en la parte inferior del cuerpo. Pero si hay mucho HTML y la red es lenta, puede llevar mucho tiempo antes de que el navegador pueda comenzar a buscar y cargar el script, por lo que colocar scripts externos en el encabezado suele ser mejor.

* Si aún desea utilizar scripts que no sean de módulo en el encabezado del documento, lo que podría impedir que se muestre toda la página y podría causar errores porque se ejecuta antes de que se analice el HTML:

Para los scripts externos, debes agregar el atributo defer(o si no necesitas que el HTML esté listo, el async) en el `<script>` elemento.
Para los scripts internos, debes envolver el código en un DOMContentLoadeddetector de eventos .

Esto está más allá del alcance del tutorial en este momento, pero a menos que necesites dar soporte a navegadores muy antiguos, no tienes que hacer esto y puedes usar `<script type="module">` en su lugar.

# Comentarios
Al igual que con HTML y CSS, es posible escribir comentarios en el código JavaScript que el navegador ignorará y que existen para proporcionar instrucciones a los demás desarrolladores sobre cómo funciona el código (y a usted, si vuelve a consultar el código después de seis meses y no recuerda lo que hizo). Los comentarios son muy útiles y debería utilizarlos con frecuencia, en particular para aplicaciones más grandes. Hay dos tipos

* Un comentario de una sola línea se escribe después de una barra diagonal doble ( //), por ejemplo

```javascript
// I am a comment
```

* Se escribe un comentario de varias líneas entre las cadenas /*y */, por ejemplo

```javascript
/*
  I am also
  a comment
*/
```

> # Nota:
>> En general, es mejor tener más comentarios que menos, pero debe tener cuidado si 
>> agrega muchos comentarios para explicar qué son las variables (los nombres de sus 
>> variables tal vez deberían ser más intuitivos) o para explicar operaciones muy simples >> (tal vez su código sea demasiado complicado).

> # Nota:
>> Muchas de las características del código que verá en JavaScript son las mismas que en >> otros lenguajes de programación: funciones, bucles, etc. La sintaxis del código parece >> diferente, pero los conceptos siguen siendo en gran medida los mismos.


# Pensando como un programador
Una de las cosas más difíciles de aprender en programación no es la sintaxis que hay que aprender, sino cómo aplicarla para resolver problemas del mundo real. Hay que empezar a pensar como programador: esto generalmente implica analizar las descripciones de lo que el programa necesita hacer, determinar qué características del código son necesarias para lograr esas cosas y cómo hacer que funcionen juntas.

Esto requiere una combinación de trabajo duro, experiencia con la sintaxis de programación y práctica, además de un poco de creatividad. Cuanto más programes, mejor te resultará. No podemos prometerte que desarrollarás un "cerebro de programador" en cinco minutos, pero te daremos muchas oportunidades para practicar el pensamiento de un programador a lo largo del curso.

# Variables

# ¿Qué es una variable?
Una variable es un contenedor de un valor, como un número que podríamos usar en una suma o una cadena que podríamos usar como parte de una oración.

Ejemplo de variable


```javascript
let count = 1;
```

esta variable, almacena un tipo de dato, en este caso es un numero.

Las variables simplemente tienen sentido y, a medida que aprendas más sobre JavaScript, comenzarán a volverse algo natural.

Una característica especial de las variables es que pueden contener prácticamente cualquier cosa, no solo cadenas y números. Las variables también pueden contener datos complejos e incluso funciones completas para hacer cosas asombrosas.

> # Nota
>> Decimos que las variables contienen valores. Es importante hacer esta distinción. Las >> variables no son los valores en sí, sino que son contenedores de valores. Puedes 
>> pensar en ellas como pequeñas cajas de cartón en las que puedes guardar cosas.

# Declarar una variable
Para utilizar una variable, primero hay que crearla; más precisamente, a esto lo llamamos declarar la variable. Para ello, escribimos la palabra clave letseguida del nombre con el que queremos llamar a la variable:

```javascript
let myName;
let myAge;
```

Aquí estamos creando dos variables llamadas `myName` y `myAge`.

> # Nota
>> En JavaScript, todas las instrucciones de código deben terminar con un punto y coma 
>> ( ;). Es posible que el código funcione correctamente en líneas individuales, pero 
>> probablemente no lo haga si escribe varias líneas de código juntas. Intente adquirir >> el hábito de incluirlo.

Puede probar si estos valores existen ahora en el entorno de ejecución escribiendo simplemente el nombre de la variable, por ejemplo

```javascript
myName;
myAge;
```

Actualmente no tienen ningún valor; son contenedores vacíos. Cuando ingrese los nombres de las variables, debería obtener un valor de undefinedretorno. Si no existen, recibirá un mensaje de error: intente escribirlos.

> # Nota
>> No confundas una variable que existe pero no tiene un valor definido con una variable >> que no existe en absoluto: son cosas muy diferentes. En la analogía de la caja que 
>> viste anteriormente, no existir significaría que no hay una caja (variable) en la que >> pueda entrar un valor. No tener un valor definido significaría que hay una caja, pero >> no tiene ningún valor dentro de ella.

Inicializando una variable
Una vez que haya declarado una variable, puede inicializarla con un valor. Para ello, escriba el nombre de la variable, seguido de un signo igual ( =), seguido del valor que desea asignarle. Por ejemplo:

```javascript
myName = "Chris";
myAge = 37;
```

Puedes declarar e inicializar una variable al mismo tiempo, de la siguiente manera:

```javascript
let myDog = "Rover";
```

Esto es probablemente lo que harás la mayor parte del tiempo, ya que es más rápido que realizar las dos acciones en dos líneas separadas.

# Una nota sobre var
Probablemente también verás una forma diferente de declarar variables, usando la varpalabra clave:


```javascript
var myName;
var myAge;
```

Cuando se creó JavaScript, esta era la única forma de declarar variables. El diseño de vares confuso y propenso a errores. Por eso, leten las versiones modernas de JavaScript se creó una nueva palabra clave para crear variables que funciona de manera algo diferente a var, solucionando sus problemas en el proceso.

A continuación se explican algunas diferencias simples. No analizaremos todas las diferencias ahora, pero comenzarás a descubrirlas a medida que aprendas más sobre JavaScript (si realmente quieres leer sobre ellas ahora, no dudes en consultar nuestra (página de referencia de let)[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let] ).

Para empezar, si escribes un programa JavaScript de varias líneas que declara e inicializa una variable, puedes declarar una variable con vardespués de inicializarla y seguirá funcionando. Por ejemplo:


```javascript
myName = "Chris";

function logName() {
  console.log(myName);
}

logName();

var myName;
```

> # Nota
>> Esto no funcionará al escribir líneas individuales en una consola de JavaScript, solo >> al ejecutar varias líneas de JavaScript en un documento web.

Esto funciona gracias a la elevación.

La elevación ya no funciona con let. Si cambiamos vara leten el ejemplo anterior, fallaría con un error. Esto es bueno: declarar una variable después de inicializarla genera un código confuso y más difícil de entender.

En segundo lugar, cuando se utiliza var, se puede declarar la misma variable tantas veces como se desee, pero con letno se puede. Lo siguiente funcionaría:

```javascript
var myName = "Chris";
var myName = "Bob";
```

Pero lo siguiente arrojaría un error en la segunda línea:

```javascript
let myName = "Chris";
let myName = "Bob";
```

Tendrías que hacer esto en su lugar:

```javascript
let myName = "Chris";
myName = "Bob";
```

Nuevamente, se trata de una decisión lingüística sensata. No hay razón para volver a declarar las variables, ya que solo hace que las cosas sean más confusas.

Por estos motivos y otros más, recomendamos que utilices leten tu código en lugar de var. A menos que escribas explícitamente compatibilidad con navegadores antiguos, ya no hay motivos para utilizarlo, varya que todos los navegadores modernos la admiten letdesde 2015.

# Actualizar una variable
Una vez que se ha inicializado una variable con un valor, puedes cambiar (o actualizar) ese valor asignándole un valor diferente.

```javascript
myName = "Bob";
myAge = 40;
```

# Un aparte sobre las reglas de denominación de variables
Puedes llamar a una variable prácticamente de cualquier forma que quieras, pero existen limitaciones. En general, deberías limitarte a utilizar solo caracteres latinos (0-9, az, A-Z) y el carácter de subrayado.

* No debes utilizar otros caracteres porque pueden provocar errores o ser difíciles de entender para una audiencia internacional.

* No utilice guiones bajos al comienzo de los nombres de variables: esto se usa en ciertas construcciones de JavaScript para significar cosas específicas, por lo que puede resultar confuso.

* No utilice números al comienzo de las variables. Esto no está permitido y provoca un error.

* Una convención segura a la que se puede adherir es la de mayúsculas y minúsculas , en la que se juntan varias palabras, se usa minúscula para la primera palabra y luego se escriben con mayúscula las palabras siguientes. Hemos estado usando esto para los nombres de las variables en el artículo hasta ahora.

* Los nombres de las variables deben ser intuitivos, de modo que describan los datos que contienen. No utilices simplemente letras o números individuales, ni frases largas.

* Las variables distinguen entre mayúsculas y minúsculas, por lo que `myage` es una variable diferente de `myAge`.

* Un último punto: también debes evitar usar palabras reservadas de JavaScript como nombres de variables (con esto nos referimos a las palabras que conforman la sintaxis real de JavaScript). Por lo tanto, no puedes usar palabras como var, function, lety forcomo nombres de variables. Los navegadores las reconocen como elementos de código diferentes y, por lo tanto, obtendrás errores.

Buenos ejemplos de nombres:

```javascript
age
myAge
init
initialColor
finalOutputValue
audio1
audio2
```

Ejemplos de malos nombres:

```javascript
1
a
_12
myage
MYAGE
var
Document
skjfndskjfnbdskjfb
thisisareallylongvariablenameman
```

# Tipos de variables
Existen distintos tipos de datos que podemos almacenar en variables. En esta sección los describiremos brevemente y, en artículos futuros, los conocerá con más detalle.

# Números
Puedes almacenar números en variables, ya sean números enteros como 30 (también llamados números enteros) o números decimales como 2.456 (también llamados números de coma flotante). No necesitas declarar tipos de variables en JavaScript, a diferencia de otros lenguajes de programación. Cuando le das un valor numérico a una variable, no incluyes comillas:

```javascript
let myAge = 17;
```

# Instrumentos de cuerda
Las cadenas son fragmentos de texto. Cuando le asignas a una variable un valor de cadena, debes encerrarlo entre comillas simples o dobles; de lo contrario, JavaScript intenta interpretarlo como otro nombre de variable.

```javascript
let dolphinGoodbye = "So long and thanks for all the fish";
```

# Booleanos
Los valores booleanos son verdaderos o falsos: pueden tener dos valores `true` o `false`. Por lo general, se utilizan para probar una condición, después de lo cual se ejecuta el código según corresponda. Por ejemplo, un caso simple sería:

```javascript
let iAmAlive = true;
```

Mientras que en realidad se utilizaría más bien así:

```javascript
let test = 6 < 3;
```

En este caso, se utiliza el operador "menor que" ( `<` ) para comprobar si 6 es menor que 3. Como es de esperar, devuelve `false`, porque 6 no es menor que 3. Aprenderá mucho más sobre estos operadores más adelante en el curso.

# Matrices
Una matriz es un único objeto que contiene varios valores encerrados entre corchetes y separados por comas.

```javascript
let myNameArray = ["Chris", "Bob", "Jim"];
let myNumberArray = [10, 15, 40];
```

Una vez definidas estas matrices, puedes acceder a cada valor por su ubicación dentro de la matriz.

```javascript
myNameArray[0]; // should return 'Chris'
myNumberArray[2]; // should return 40
```

Los corchetes especifican un valor de índice correspondiente a la posición del valor que desea que se devuelva. Es posible que haya notado que las matrices en JavaScript tienen un índice cero: el primer elemento está en el índice 0.

# Objetos
En programación, un objeto es una estructura de código que modela un objeto de la vida real. Puedes tener un objeto que represente una caja y que contenga información sobre su ancho, largo y alto, o puedes tener un objeto que represente a una persona y que contenga datos sobre su nombre, altura, peso, qué idioma habla, cómo saludarla y más.

```javascript
let dog = { name: "Spot", breed: "Dalmatian" };
```

Para recuperar la información almacenada en el objeto, puede utilizar la siguiente sintaxis:

```javascript
dog.name;
```

Tipificación dinámica
JavaScript es un "lenguaje tipado dinámicamente", lo que significa que, a diferencia de otros lenguajes, no es necesario especificar qué tipo de datos contendrá una variable (números, cadenas, matrices, etc.).

Por ejemplo, si declara una variable y le asigna un valor entre comillas, el navegador trata la variable como una cadena:

```javascript
let myString = "Hello";
```

Incluso si el valor entre comillas son solo dígitos, sigue siendo una cadena, no un número, así que tenga cuidado:

```javascript
let myNumber = "500"; // oops, this is still a string
typeof myNumber;
myNumber = 500; // much better — now this is a number
typeof myNumber;
```

Notarás que estamos usando un operador especial llamado typeof: este devuelve el tipo de datos de la variable que escribes después. La primera vez que se llama, debería devolver string, ya que en ese momento la myNumbervariable contiene una cadena, '500'. Observa qué devuelve la segunda vez que lo llamas.

# Constantes en JavaScript
Además de las variables, puedes declarar constantes. Son como las variables, excepto que:

* Debes inicializarlos cuando los declaras.

* No puedes asignarles un nuevo valor después de haberlos inicializado.

Por ejemplo, al usar `let` puedes declarar una variable sin inicializarla:

```javascript
let count;
```

Si intentas hacer esto, constverás un error:

```javascript
const count;
```

De manera similar, letpuedes inicializar una variable y luego asignarle un nuevo valor (esto también se llama reasignar la variable):

```javascript
let count = 1;
count = 2;
```

Si intentas hacer esto, constverás un error:

```javascript
const count = 1;
count = 2;
```

Tenga en cuenta que, si bien una constante en JavaScript siempre debe nombrar el mismo valor, puede cambiar el contenido del valor que nombra. Esta no es una distinción útil para tipos simples como números o booleanos, pero considere un objeto:

```javascript
const bird = { species: "Kestrel" };
console.log(bird.species); // "Kestrel"
```

Puede actualizar, agregar o eliminar propiedades de un objeto declarado utilizando const, porque aunque el contenido del objeto haya cambiado, la constante sigue apuntando al mismo objeto:

```javascript
bird.species = "Striated Caracara";
console.log(bird.species); // "Striated Caracara"
```

# Cuándo usar const y cuándo usar let
Si no puedes hacer tanto con constcomo con let, ¿por qué preferirías usarlo en lugar de let? De hecho, constes muy útil. Si usas constpara nombrar un valor, le dice a cualquier persona que mire tu código que este nombre nunca se asignará a un valor diferente. Cada vez que vean este nombre, sabrán a qué se refiere.

En este curso, adoptamos el siguiente principio sobre cuándo utilizar lety cuándo utilizar const:

Úselo constcuando pueda y letcuando tenga que hacerlo.

Esto significa que si puedes inicializar una variable cuando la declaras y no necesitas reasignarla más tarde, conviértela en una constante.

# [**¿Qué es la Asincronía?**](https://lenguajejs.com/asincronia/introduccion/que-es/)

La **asincronía** es uno de los conceptos principales que existe en el mundo de Javascript. Cuando comenzamos, es muy común trabajar con código **síncrono** (***secuencial***), sin embargo, llegado a un punto necesitaremos trabajar con código **asíncrono**, el cuál puede ser muy frustrante si no lo entendemos bien.

En programación, cuando hablamos de **sincronía**, nos referimos a una forma de ejecutar el código. Cuando comenzamos a programar, normalmente realizamos tareas de forma **síncrona**, llevando a cabo tareas **secuenciales** que se ejecutan una detrás de otra, de modo que el orden o flujo del programa es sencillo y fácil de observar en el código:

```css
primera_funcion();    // Tarea 1: Se ejecuta primero
segunda_funcion();    // Tarea 2: Se ejecuta cuando termina primera_funcion()
tercera_funcion();    // Tarea 3: Se ejecuta cuando termina segunda_funcion()
```

Sin embargo, en el mundo de la programación, tarde o temprano necesitaremos realizar operaciones **asíncronas**, especialmente en ciertos lenguajes como Javascript, donde tenemos que realizar tareas **que tienen que esperar a que ocurra un determinado suceso**.

Este suceso tiene varias características:

- 1️⃣ Generalmente, no depende de nosotros
- 2️⃣ No solemos saber cuando va a ocurrir
- 3️⃣ A veces, ni siquiera sabemos si va a ocurrir

Nuestro código tiene que saber gestionar esas características, y reaccionar sólo cuando dicho suceso ocurra.

# [**Lenguaje no bloqueante**](https://lenguajejs.com/asincronia/introduccion/que-es/#lenguaje-no-bloqueante)

Otro concepto importante es saber cuando el código es **bloqueante** o no. Observa el fragmento de código anterior. Hasta que la **`segunda_funcion()`** termine, la **`tercera_funcion()`** no comenzará. En ese caso, **`segunda_funcion()`** **está bloqueando** **`tercera_funcion()`**.

Además, esto es especialmente importante en casos donde, por ejemplo, **`segunda_funcion()`** necesite información de un sistema ajeno al nuestro (***por ejemplo, que el usuario escriba información por teclado***). Hasta que el usuario no realice esa acción, al ser bloqueante, no se ejecutará el código que hay a continuación.

<aside>
💡

Esta es la forma de trabajar de muchos lenguajes, sin embargo, sería muy interesante que nuestro código «se quede a la espera» mientras ejecutamos y realizamos otras tareas.

</aside>

Por si acaso no haya quedado claro, imaginemos que la **`segunda_funcion()`** del ejemplo anterior realiza una tarea que depende de otros, como por ejemplo un click de ratón del usuario. Si hablasemos de un **código bloqueante**, hasta que el usuario no haga click, no se seguiría ejecutando el resto del código, sino que se quedaría bloqueado esperando a que se terminase esa segunda tarea:

![image.png](attachment:79f95b21-08a9-4e5c-9b80-125187baaaff:image.png)

Cuando hablamos de Javascript, habitualmente nos referimos a él como un lenguaje que puede ser **no bloqueante**. Con esto queremos decir que podemos conseguir que las tareas que realizamos no se quedan bloqueadas. Javascript puede mover una tarea que depende de otra a una lista de **tareas en espera (pendientes)** a las que irá «prestándole atención» a medida que lo necesite, pudiendo continuar con el resto de tareas a continuación de nuestro código.

# [**¿Qué es la asincronía?**](https://lenguajejs.com/asincronia/introduccion/que-es/#qu%C3%A9-es-la-asincron%C3%ADa)

La **asincronía** es como se le llama a esta forma de trabajar donde tenemos que ir programando pensando en tareas futuras que aún no han ocurrido, pero que en algún momento ocurrirán.

Además, ten en cuenta que esta situación aún se puede complicar:

- 1️⃣ Pueden existir **múltiples** tareas asíncronas
- 2️⃣ Las tareas pueden terminar realizandose correctamente
- 3️⃣ Las tareas pueden terminar fallando y no realizarse
- 4️⃣ Las tareas pueden quedarse pendientes de forma infinita y nunca realizarse o fallar.
- 5️⃣ Las tareas pueden depender a su vez de otras tareas.
- 6️⃣ Las tareas pueden tardar poco o tardar mucho.

Así que necesitamos mecanismos para controlar estas tareas, que es lo que veremos en los siguientes artículos. Pero antes, vamos a ver algunos ejemplos de tareas que son asíncronas.

# [**Ejemplos de tareas asíncronas**](https://lenguajejs.com/asincronia/introduccion/que-es/#ejemplos-de-tareas-as%C3%ADncronas)

En Javascript no todas las tareas son asíncronas, pero hay ciertas tareas que si lo son, y probablemente se entiendan mejor con ejemplos reales:

- Descargarse un archivo **`.json`** de otra web.
- Reproducir un **`.mp3`** desde otra web.
- Un botón o campo de datos donde el usuario debe activar un mecanismo.
- Una orden al sintetizador de voz del navegador para que lea un mensaje.
- Una comunicación con un sensor del smartphone.

Todos estos ejemplos se realizan mediante **asincronia**, ya que deben realizar una tarea que podría tardar y bloquear la ejecución del programa (***si tarda mucho o no ocurre***):

- La descarga de un fichero muy grande o desde un servidor lento
- Una conexión a internet muy lenta o con poca cobertura
- Un usuario que está ausente y no ha proporcionado la información
- Un sensor de smartphone que es lento al activarse o transmitir datos

Creo que con estos ejemplos, tenemos claro que mediante **código síncrono** es complicado gestionar estas situaciones. Por lo tanto, necesitamos una forma de gestionarlas.

# [**¿Cómo gestionar la asincronía?**](https://lenguajejs.com/asincronia/introduccion/que-es/#c%C3%B3mo-gestionar-la-asincron%C3%ADa)

Debemos aprender mecanismos para dejar claro en nuestro código Javascript, que ciertas tareas tienen que procesarse de forma asíncrona para quedarse a la espera, y otras deben ejecutarse de forma síncrona.

En Javascript existen varias formas de gestionar la **asincronía**. Observa en la siguiente tabla los principales mecanismos:

| **Mecanismo** | **Descripción** | **Más info** |
| --- | --- | --- |
| Mediante **`callbacks`** | Probablemente, la forma más clásica de gestionar la asincronía. | [Ver Callbacks](https://lenguajejs.com/javascript/asincronia/callbacks/) |
| Mediante **`promesas`** | Mecanismo moderno para gestionar la asincronía de forma no bloqueante. | [Ver Promesas](https://lenguajejs.com/javascript/asincronia/promesas/) |
| Mediante **`async`**/**`await`** | Una forma simplificada de manejar promesas, pero bloqueante. | [Ver Async/Await](https://lenguajejs.com/javascript/asincronia/async-await/) |
| Mediante **`top-level await`** | Una variación de la anterior, donde no es necesario usar **`async`** en determinados contextos. |  |
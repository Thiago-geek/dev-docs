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

## [El contexto de renderización](https://developer.mozilla.org/es/docs/Web/API/Canvas_API/Tutorial/Basic_usage#el_contexto_de_renderizaci%C3%B3n)

[`<canvas>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/canvas) crea un lienzo de dibujo fijado que expone uno o mas contextos renderizados, los cuales son usados para crear y manipular el contenido mostrado. Nos enfocaremos en renderizacion de contextos 2D. Otros contextos deberan proveer diferentes tipos de renderizaciones; por ejemplo, [WebGL](https://developer.mozilla.org/es/docs/Web/API/WebGL_API) usa un 3D contexto ("experimental-webgl") basado sobre [OpenGL ES](https://www.khronos.org/opengles/).

El canvas esta inicialmente en blanco. Para mostrar alguna cosa, un script primero necesita acceder al contexto a renderizar y dibujar sobre este. El elemento [`<canvas>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/canvas) tiene un [method](https://developer.mozilla.org/es/docs/Web/API/HTMLCanvasElement#methods) llamado `getContext()`, usado para obtener el contexto a renderizar y sus funciones de dibujo. `getContext()` toma un parametro, el tipo de contexto. Para graficos 2D, como los que cubre este tutorial, su especificacion es "2d".

```jsx
var canvas = document.getElementById("tutorial");
var ctx = canvas.getContext("2d");
```

La primera linea regresa el nodo DOM para el elemento [`<canvas>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/canvas) llamando al metodo [`document.getElementById()`](https://developer.mozilla.org/es/docs/Web/API/Document/getElementById). Una vez tu tienes el elemento nodo, tu puedes acceder al contexto de dibujo usando su metodo `getContext()`.

# **Window: requestAnimationFrame()**

El **`window.requestAnimationFrame()`**método le indica al navegador que desea realizar una animación. Le solicita que llame a una función de devolución de llamada proporcionada por el usuario antes del siguiente repintado.

La frecuencia de las llamadas a la función de devolución de llamada generalmente coincide con la frecuencia de actualización de la pantalla. La frecuencia de actualización más común es 60 Hz (60 ciclos/fotogramas por segundo), aunque también se utilizan ampliamente 75 Hz, 120 Hz y 144 Hz. `requestAnimationFrame()`Las llamadas se pausan en la mayoría de los navegadores cuando se ejecutan en pestañas en segundo plano o en mensajes ocultos [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), con el fin de mejorar el rendimiento y la duración de la batería.

# [**La etiqueta HTML <canvas>**](https://lenguajejs.com/javascript/canvas/etiqueta-html-canvas/)

## **Primeros pasos a la programación gráfica con Javascript**

En HTML, existe un elemento HTML llamado **`<canvas>`** que sirve como lienzo en blanco donde se puede dibujar mediante programación. 

Aunque se trata de un elemento HTML, toda la lógica de programación se realiza mediante Javascript, utilizando su propia API.

# [**El elemento `<canvas>`**](https://lenguajejs.com/javascript/canvas/etiqueta-html-canvas/#el-elemento-canvas)

Para comenzar a utilizar el elemento **`<canvas>`**, básicamente lo creamos en el HTML y lo localizamos desde Javascript mediante el DOM. También es posible crearlo desde Javascript mediante **`document.createElement()`** y añadirlo al HTML si lo preferimos.

Los primeros pasos suelen ser indicar el tamaño que tendrá el lienzo, para poder verlo en la página. Eso lo haremos simplemente dándole un **`width`** y **`height`** a nuestro elemento **`<canvas>`**:

```jsx
const canvas = document.querySelector("canvas");
  canvas.width = 320;
  canvas.height = 240;
  canvas.style.background = "#000";
```

Ten en cuenta que en la última línea le estamos dando un color de fondo negro al canvas mediante CSS. Esto lo estamos haciendo ahora de esta forma porque es sencillo y rápido hacerlo mediante JS/CSS, pero generalmente se utiliza el **`fill()`** o **`fillRect()`** de canvas, que veremos un poco más adelante.

# [**El contexto del canvas**](https://lenguajejs.com/javascript/canvas/etiqueta-html-canvas/#el-contexto-del-canvas)

Para trabajar con canvas, tenemos que crear un **contexto**, que es el objeto que nos permite controlar nuestro lienzo. Este objeto se toma del canvas mediante el método **`.getContext()`** y hay que indicarle por parámetro el tipo de lienzo que queremos:

```jsx
 const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 320;
  canvas.height = 240;
  canvas.style.background = "#ccc";
```

Podemos establecer diferentes tipos diferentes de lienzo:

| **Tipo** | **Objeto** | **Orientación del contexto** |
| --- | --- | --- |
| **`"2d"`** | **`CanvasRenderingContext2D`** | Gráficos 2D (lineas, formas, texto, imágenes...). |
| **`"webgl2"`** | **`WebGL2RenderingContext`** | API basada en OpenGL ES 3.0 para 2D/3D con aceleración por hardware. |
| **`"webgpu"`** | **`GPUCanvasContext`** | Gráficos de alta eficiencia (optimizado para tarjetas gráficas modernas). |
| **`"bitmaprenderer"`** | **`ImageBitmapRenderingContext`** | Orientado para renderizar imágenes con alto rendimiento. |

En esta documentación nos vamos a centrar en **gráficos 2D**, que son los más sencillos para comenzar. 

# [**Dibujar en el canvas**](https://lenguajejs.com/javascript/canvas/etiqueta-html-canvas/#dibujar-en-el-canvas)

Una vez hemos creado nuestro contexto, que hemos almacenado en una variable llamada **`ctx`**, vamos a trabajar con varios métodos para dibujar en el canvas.

Antes de nada, ten en cuenta que vamos a utilizar propiedades como **`.fillStyle`** o **`.strokeStyle`** para establecer estilo y dibujar rellenos o trazos, como veremos en los ejemplos. La tabla que ves a continuación son algunas de las siguientes funciones que tenemos disponibles para utilizar con nuestro contexto 2D de canvas:

| **Método** | **Descripción** |
| --- | --- |
| **Formas geométricas** |  |
| **`.beginPath()`** / **`.closePath()`** | Comienza o cierra una ruta. |
| **`.ellipse()`** | Crea un círculo ovalado (elipse) indicando centro, radios, ángulos, etc. |
| **`.rect()`** | Crea un rectángulo con un ancho y altura indicado. |
| **`.stroke()`** / **`.fill()`** | Dibuja el contorno de la ruta, y rellena el interior. |
| **`.moveTo()`** / **`.lineTo()`** | Se mueve a una coordenada sin dibujar trazo o dibujándolo. |
| **Dibujo directo** |  |
| **`.strokeRect()`** / **`.fillRect()`** | Dibuja el contorno o el relleno de un rectángulo. |
| **`.strokeText()`** / **`.fillText()`** | Dibuja el contorno o el relleno de un texto. |
| **`.roundRect()`** | Dibuja un rectángulo con bordes redondeados. |
| **`.clearRect()`** | Borra el lienzo completo o una porción de él. |
| **Curvas** |  |
| **`.arc()`** / **`.arcTo()`** | Dibuja el arco de un círculo o el arco entre dos líneas. |
| **`.bezierCurveTo()`** | Dibuja una curva bézier cúbica a partir de un punto con 3 puntos de control. |
| **`.quadraticCurveTo()`** | Dibuja una curva cuadrática a partir de un punto, con 2 puntos de control. |

# [**Estado del canvas**](https://lenguajejs.com/javascript/canvas/etiqueta-html-canvas/#estado-del-canvas)

Debes saber que nuestro **`<canvas>`** tiene la posibilidad de guardar su estado en una estructura de tipo pila y recuperarlo posteriormente. Cuando hablamos de **estado** nos referimos a propiedades como **`.fillStyle`**, **`.strokeStyle`**, **`.globalAlpha`**, etc... También transformaciones como **`translate`**, **`scale`**, **`rotate`** o recortes con **`.clip()`**.

Utilizando el método **`.save()`** guardamos en la pila, mientras que con **`.restore()`** recuperamos el último estado guardado.

Observa el siguiente ejemplo, donde:

- 1️⃣ Establecemos un color rosa de relleno y guardamos el estado.
- 2️⃣ Cambiamos el color de relleno a verde.
- 3️⃣ Cada segundo, dibujamos un cuadradito (verde).
- 4️⃣ Cuando hagamos click, recuperamos el estado y lo pintará rosa.

```jsx
 const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;
  canvas.style.background = "#ccc";    // lightgrey

  // Guardamos el estado con el color de relleno rosa
  ctx.fillStyle = "deeppink";
  ctx.save();

  // Cada segundo se añadirá un nuevo cuadrado verde
  ctx.fillStyle = "green";
  setInterval(() => {
    const x = Math.floor(Math.random() * canvas.width);
    const y = Math.floor(Math.random() * canvas.height);
    ctx.fillRect(x, y, 50, 50);
  }, 1000);

  // Cuando hagas click, el color se restaura a rosa
  canvas.addEventListener("click", () => ctx.restore());
```

Además de estos métodos para manejar el estado, también podemos realizar transformaciones o acciones similares. Estos son los métodos que tenemos en canvas para realizarlos:

| **Método** | **Descripción** |
| --- | --- |
| **Estado** |  |
| **`.save()`** | Guarda el estado actual del lienzo en una pila. |
| **`.restore()`** | Restaura el último estado guardado en la pila con **`.save()`**. |
| **`.reset()`** | Reinicia el estado del lienzo. Experimental, se recomienda usar **`.resetTransform()`**. |
| **Transformaciones** |  |
| **`.transform()`** | Aplica una transformación acumulativa, respetando la transformación previa. |
| **`.setTransform()`** | Aplica una transformación, reemplazando cualquier transformación previa. |
| **`.getTransform()`** | Devuelve un objeto **`DOMMatrix`** con la transformación actual del lienzo. |
| **`.resetTransform()`** | Elimina todas las transformaciones previas. Igual a **`.setTransform(1, 0, 0, 1, 0, 0)`**. |
| **`.scale()`** | Escala según los factores proporcionados. |
| **`.translate()`** | Desplaza a un nuevo punto definido por **`(x, y)`**. |
| **`.rotate()`** | Rota en torno a su origen actual (ángulo en radianes). |
| **`.clip()`** | Recorta una región particular del lienzo. |

> Los métodos de transformación funcionan de forma muy similar a las transformaciones de CSS. Ten cuidado al utilizarlos, ya que actuan sobre todo el lienzo.
> 

# [**Animaciones con <canvas>**](https://lenguajejs.com/javascript/canvas/bucle-animaciones/)

## **El bucle de animación y requestAnimationFrame**

 vimos los primeros pasos al utilizar el elemento **`<canvas>`** y como dibujar formas básicas en él. Esto está bien como primera aproximación, pero generalmente, queremos crear animaciones o minijuegos, por lo que necesitamos preparar lo que se llama **el bucle de juego** o **el bucle de animación**.

# [**El bucle de animación**](https://lenguajejs.com/javascript/canvas/bucle-animaciones/#el-bucle-de-animaci%C3%B3n)

Este bucle es una función que se ejecuta continuamente en un intervalo de tiempo. Este intervalo de tiempo se llama **frecuencia de actualización** o **FPS** (***Frames per second***). Por ejemplo, si queremos que la animación se mueva a una velocidad de **`60fps`**, entonces se debe ejecutar cada **`1/60`**.

El código creará un círculo relleno de color rosa que rebotará verticalmente en pantalla. Ten en cuenta que para generar una animación, se suele tener una **estructura general** donde realizamos varias tareas. Esta sería una buena primera aproximación:

- 1️⃣ Fuera del bucle, **inicialización** (tareas iniciales que sólo se ejecutan una vez)
- 2️⃣ Dentro del bucle, **actualización** (tareas de lógica, cálculo de datos)
- 3️⃣ Dentro del bucle, **renderización** (tareas de dibujado y pintado)
- 4️⃣ Dentro del bucle, **reiniciar bucle** (decidir si continuar bucle o parar)

Una primera buena práctica es diferenciar el código que pinta del código que actualiza los datos de la animación o juego. Veamos una primera implementación definiendo estos 4 grupos:

En este fragmento de código, establecemos las coordenadas **`x`** e **`y`** donde estará el círculo. Las variables **`dx`** y **`dy`** definen la velocidad con la que avanza en cada eje y **`radius`** es el radio del círculo. Además, establecemos la velocidad de actualización del bucle en **`FPS`**:

```jsx
let x = 100, y = 100, dx = 2, dy = 2, radius = 25;
const FPS = 1000 / 60;
```

En este fragmento de código simplemente actualizamos la coordenada **`y`** (***eje vertical***) aumentándolo en la velocidad **`dy`**. También comprobamos si se ha llegado al límite inferior o superior, en cuyo caso, invertimos el signo de la velocidad:

```jsx
y += dy
if (y + radius > canvas.height || y - radius < 0) dy *= -1;
```

Por último, en esta parte realizamos las tareas de pintado en el canvas. Borramos el lienzo con **`clearRect()`** en cada fotograma para evitar que se acumulen, creamos un trayecto y dibujamos el círculo relleno:

```jsx
ctx.clearRect(0, 0, canvas.width, canvas.height);
ctx.beginPath();
ctx.arc(x, y, radius, 0, Math.PI * 2);
ctx.fillStyle = "deeppink";
ctx.fill();
ctx.closePath();
```

Sin embargo, aunque podemos ver la estructura general, el código es muy caótico si lo colocamos secuencialmente, por lo que convendría organizarlo un poco, así que vamos a ello:

- 1️⃣ Fuera de **`gameLoop()`**, **inicialización** (coordenadas, FPS, radio del círculo, etc...)
- 2️⃣ Dentro de **`update()`**, **actualización** (mover el círculo y comprobar si ha llegado a un límite)
- 3️⃣ Dentro de **`draw()`**, **renderización** (borrar lienzo y dibujar posición del círculo)
- 4️⃣ Dentro de **`gameLoop()`**, **reiniciar bucle** (simplemente, volver a ejecutar el bucle)

Utilizando las secciones que mencionamos anteriormente, vamos a organizarlo en funciones:

```jsx
  const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;

  // Inicialización
  let y = 100, dy = 2;
  const x = 100, dx = 2, radius = 25;
  const FPS = 1000 / 60;

  // Actualización de lógica
  const update = () => {
    y += dy
    if (y + radius > canvas.height || y - radius < 0) dy *= -1;
  }

  // Renderizado y pintado
  const draw = () => {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.beginPath();
    ctx.arc(x, y, radius, 0, Math.PI * 2);
    ctx.fillStyle = "deeppink";
    ctx.fill();
    ctx.closePath();
  }

  // Bucle del juego (update, draw, reinicio)
  function gameLoop() {
    update();
    draw();
    setTimeout(gameLoop, FPS);
  }

  gameLoop();
```

Observa que en este ejemplo el bucle **`gameLoop`** es un bucle infinito que nunca para (***hasta que se cierre el navegador***). Si queremos que en algún momento pare la animación, tendríamos que establecer una condición para que en un caso concreto, no se ejecute más el **`gameLoop`**.

# [**Mejorando con `requestAnimationFrame()`**](https://lenguajejs.com/javascript/canvas/bucle-animaciones/#mejorando-con-requestanimationframe)

En el ejemplo anterior, utilizamos la función **`setTimeout()`** que programa la ejecución de una función tras un tiempo concreto. Aunque funciona correctamente, el uso de **`setTimeout()`** puede acarrearnos ciertos problemas en casos especificos, como que no se sincronice correctamente con el monitor (***ejecuta la animación más rápido o más lento y pierde fotogramas o se desincroniza***), no suspende la animación si la pestaña del navegador no está activa (***uso innecesario de recursos***), etc.

| **Característica** | **`setInterval()` / `setTimeout()`** | **`requestAnimationFrame()`** |
| --- | --- | --- |
| Sincronización con el monitor | ❌ No sincronizado | ✅ Sincronizado |
| Eficiencia en segundo plano | ❌ Sigue ejecutándose | ✅ Se pausa automáticamente |
| Precisión temporal | ❌ Puede variar | ✅ Alta precisión |
| Uso del tiempo | ❌ No optimizado | ✅ Optimizado por el navegador |
| Flexibilidad de FPS | Manual | Automático |

Para evitar estos problemas vamos a utilizar **`requestAnimationFrame()`**, que lo gestiona todo mejor:

```jsx
  const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;

  // Inicialización
  let y = 100, dy = 2;
  const x = 100, dx = 2, radius = 25;

  // Actualización de lógica
  const update = () => {
    y += dy
    if (y + radius > canvas.height || y - radius < 0) dy *= -1;
  }

  // Renderizado y pintado
  const draw = () => {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.beginPath();
    ctx.arc(x, y, radius, 0, Math.PI * 2);
    ctx.fillStyle = "deeppink";
    ctx.fill();
    ctx.closePath();
  }

  // Bucle del juego (update, draw, reinicio)
  function gameLoop() {
    update();
    draw();
    requestAnimationFrame(gameLoop);
  }

  gameLoop();
```

Comprobarás que ahora, no tenemos que definir los **`FPS`**, y la animación va automáticamente más fluida. Si queremos cambiar la velocidad del elemento, tendríamos que cambiar la lógica de nuestra animación, en nuestro caso el valor de **`dy`**.

# [**Imágenes con <canvas>**](https://lenguajejs.com/javascript/canvas/imagenes/)

## **Trabajando con imágenes en elementos canvas**

Uno de los detalles más interesantes de trabajar con **`<canvas>`** es que puedes dibujar imágenes en el lienzo, utilizando la potencia de Javascript para realizar cualquier tarea adicional.

Para ello, utilizaremos el método **`.drawImage()`** que podemos utilizarlo de varias formas diferentes:

| **Método** | **Descripción** |
| --- | --- |
| **`ctx.drawImage(image, x, y)`** | Dibuja la imagen en las coordenadas **`x,y`**. |
| **`ctx.drawImage(image, x, y, w, h)`** | Dibuja la imagen en **`x,y`** con tamaño **`WxH`**. |
| **`ctx.drawImage(image, frame_x, frame_y, frame_w, frame_h, x, y, w, h)`** | Dibuja un frame concreto en el lienzo. |

Además, ten en cuenta que en **`image`** podemos indicar varios tipos de elementos, no solo imágenes:

| **Tipo de imagen** | **Descripción** |
| --- | --- |
| **`HTMLImageElement`** | Una elemento **`<img>`** de HTML con una imagen en formatos como **`jpg`**, **`png`**, **`webp`**, **`avif`**, **`gif`**... |
| **`SVGImageElement`** | Una elemento **`<svg>`** de HTML con una imagen vectorial. |
| **`HTMLVideoElement`** | Un elemento **`<video>`** de HTML con un video en formatos como **`mp4`**, **`webm`**... |
| **`HTMLCanvasElement`** | Otro elemento **`<canvas>`** de HTML utilizado como "fuente". |
| **`ImageBitmap`** | Una imagen de mapa de bits, normalmente creada para trabajar sin latencia. |
| **`OffscreenCanvas`** | Un elemento **`<canvas>`** que no está atado al DOM y puede estar fuera de pantalla. |
| **`VideoFrame`** | Un fotograma de un video específico. |

Primero, vamos a centrarnos en las dos primeras trabajando con una imagen simple, ya que son las más sencillas. Luego, trabajaremos con un spritesheet (***imagen con varios frames***) y utilizaremos la última.

> Un fallo muy común al dibujar imágenes en canvas es pensar que la imagen está cargada inmediatamente. Esa tarea depende de la conexión, por lo que hay que esperar a que esté cargada. Para evitarlo, escucharemos un evento load para asegurarnos.
> 

Observa que en nuestro caso concreto estamos usando imágenes **pixel art**. Hemos desactivado **`imageSmoothingEnabled`** para que no suavice la imagen al ampliarla, ya que en las imágenes pixel art no se usa ese suavizado.

# [**Exportación desde un <canvas>**](https://lenguajejs.com/javascript/canvas/exportar/)

## **Guardar el contenido de un canvas**

Imaginemos que tenemos la necesidad de exportar en algún tipo de formato multimedia el contenido que tenemos en nuestro elemento **`<canvas>`**.

# [**Exportar un canvas**](https://lenguajejs.com/javascript/canvas/exportar/#exportar-un-canvas)

Nuestro elemento **`<canvas>`** tiene tres métodos interesantes para exportar su contenido:

| **Método** | **Descripción** |
| --- | --- |
| **`.toDataURL(type, quality)`** | Convierte el lienzo en una imagen formato **`type`** representada como  Data URI. |
| **`.toBlob(fn, type, quality)`** | Convierte el lienzo en un BLOB (Binary Large Object) para manipulación eficiente. |
| **`.captureStream()`** | Permite capturar el contenido del lienzo como un stream de datos, convertible a video. |

Vamos a ver varios ejemplos donde utilizaremos cada uno de ellos.

Mediante el método **`.toDataURL()`** podemos convertir la imagen que se ve en el lienzo en una imagen de tipo Data URI, es decir, una cadena de texto (***generalmente, muy grande***) que contiene la información de la imagen, y que se puede mostrar al colocarla como URL.

En este ejemplo, guardamos dicho  en **`dataURL`** lo añadimos al atributo **`src`** de una **`<img>`** HTML. Con ello, es suficiente para mostrar la imagen:

```jsx
  const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;
  canvas.style.background = "#ccc";

  ctx.fillStyle = "blue";
  ctx.fillRect(50, 50, 100, 100);

  // Convierte el lienzo a Data URI en formato PNG
  const dataURL = canvas.toDataURL("image/png", 1.0);
  const img = document.createElement("img");
  img.src = dataURL;
  document.body.append(img);
```

Una forma alternativa de guardar la imagen del canvas, es utilizando el método **`.toBlob()`**. Este método convierte la información del canvas en un BLOB (***Binary Large Object***), que es un formato que permite almacenar grandes cantidades inmutables de datos binarios.

Una de las características importantes de estos BLOB es que son ideales para trabajar con grandes cantidades de datos, ya que se manipulan como referencias a memoria, en lugar de como cadenas de texto.

```jsx
  const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;
  canvas.style.background = "#ccc";

  ctx.fillStyle = "blue";
  ctx.fillRect(50, 50, 100, 100);

  // Convierte el lienzo en un BLOB y permite descargarlo mediante un enlace
  canvas.toBlob((blob) => {
    const a = document.createElement("a");
    a.href = URL.createObjectURL(blob);
    console.log({ blob, url: a.href })
    a.download = "canvas-image.png";
    a.textContent = "Descargar";
    document.body.append(a);
  }, "image/png", 1.0);
```

Por último, también podemos crear un video a partir de una animación de un elemento canvas. Para ello, vamos a utilizar el método **`.captureStream()`**, que permite ir capturando los fotogramas del canvas, para crear un video. Vamos a explicar los detalles clave que hemos hecho:

- 1️⃣ En el canvas, se muestra un cuadrado que va cambiando de color de forma aleatoria.
- 2️⃣ Si pulsamos en el botón **`Record`** comenzamos a capturar los datos del canvas y guardándolos.
- 3️⃣ En **`recordedChunks`** vamos guardando los datos capturados en cuanto hay disponibles.
- 4️⃣ Con el **`MediaRecorder`** establecemos un mecanismo para grabar en video.
- 5️⃣ Si pulsamos en el botón **`Stop record`**, paramos la grabación y activamos un enlace de descarga.
- 6️⃣ Al pulsar en ese enlace, el se descarga el video en formato MP4.

Echemos un vistazo a dicho código:

```html
<canvas></canvas><button class="record">Record</button><a class="download"></a><script>
  const recordButton = document.querySelector(".record");
  const downloadLink = document.querySelector(".download");
  const canvas = document.querySelector("canvas");
  const ctx = canvas.getContext("2d");
  canvas.width = 200;
  canvas.height = 200;
  canvas.style.background = "#ccc";

  ctx.fillStyle = "red";
  ctx.fillRect(50, 50, 100, 100);

  // Dibuja un cuadrado de un color aleatorio cada 0.5seg
  setInterval(() => {
    const r = Math.random() * 255;
    const g = Math.random() * 255;
    const b = Math.random() * 255;
    ctx.fillStyle = `rgb(${r}, ${g}, ${b})`;
    ctx.fillRect(50, 50, 100, 100);
  }, 500);

  let mediaRecorder;
  let recordedChunks = [];

  recordButton.addEventListener("click", () => {
    const stream = canvas.captureStream();
    const video = document.createElement("video");
    video.muted = true;
    video.autoplay = true;
    video.srcObject = stream;

    if (!mediaRecorder || mediaRecorder.state === "inactive") {
      recordedChunks = [];
      mediaRecorder = new MediaRecorder(stream, { mimeType: "video/mp4" });

      mediaRecorder.addEventListener("dataavailable", (event) => {
        if (event.data.size > 0) {
          recordedChunks.push(event.data);
        }
      });

      mediaRecorder.addEventListener("stop", () => {
        const blob = new Blob(recordedChunks, { type: "video/mp4" });
        const url = URL.createObjectURL(blob);
        downloadLink.href = url;
        downloadLink.textContent = "Download";
        downloadLink.download = "canvas-animation.mp4";
      });

      mediaRecorder.start();
      recordButton.textContent = "Stop Recording";
    } else {
      mediaRecorder.stop();
      recordButton.textContent = "Start Recording";
    }
  });
</script>
```

Con estos mecanismos, podemos utilizar un elemento HTML **`<canvas>`** para generar información multimedia, tanto en imagen como en video, permitiéndo descargarlo y guardarlo en nuestro sistema.

# [**URL en Javascript**](https://lenguajejs.com/javascript/peticiones-http/url/)

## **Trabajando con direcciones URL en Javascript**

Normalmente, cuando tenemos que trabajar con una **dirección web** (***URL***) en Javascript, lo más habitual es utilizar un tipo de dato  donde almacenamos dicha **URL**. En la mayoría de los casos, esto suele ser suficiente. Sin embargo, si necesitamos hacer ciertas operaciones con la URL donde tengamos que modificar o acceder a ciertas partes específicas de la URL, se podría complicar un poco.

# [**El objeto URL**](https://lenguajejs.com/javascript/peticiones-http/url/#el-objeto-url)

Si necesitamos acceder a partes específicas de una URL, o incluso modificarlas, tenemos un  de tipo  especial para estos casos, que será mucho más cómodo que trabajar con el  (***y contemplar todos los posibles casos que podrían ocurrir***). Su funcionamiento es el siguiente:

```jsx
const url = new URL("https://manz.dev/");

url.protocol      // "https:"
url.hostname      // "manz.dev"
url.pathname      // "/"
```

Como puedes ver, se puede ir accediendo a diferentes propiedades del objeto **`url`** que hemos generado a partir del  de la URL para obtener partes específicas de la dirección web.

# [**Partes de una URL**](https://lenguajejs.com/javascript/peticiones-http/url/#partes-de-una-url)

Para explicar como trabajar con **URL** en Javascript, antes necesitamos analizar bien la estructura de una URL y examinar las diferentes partes que la componen, para tener bien claro antes de trabajar con nuestro código Javascript.

![image.png](attachment:76624eef-d2ca-459d-834f-d6d4fb3638c6:image.png)

Vamos a generar dos **objetos**: **`url`** y **`local`**. Los crearemos a partir de dos  con dos URL específicas que pasaremos por parámetro, mediante un **`new URL()`**:

```jsx
const url = new URL("https://sub.manz.dev/path/page.html#anchor");
const local = new URL("http://manz:12345@localhost:8000/path/file.mp3");
```

Un objeto  contiene una serie de propiedades para identificar partes concretas de la URL generada:

| **Propiedad** | **Descripción** | **Ejemplo url** | **Ejemplo local** |
| --- | --- | --- | --- |
| **`.protocol`** | Protocolo de comunicación usado. | **`https:`** | **`http:`** |
| **`.hostname`** | Dominio completo (subdominio + dominio). | **`sub.manz.dev`** | **`localhost`** |
| **`.host`** | Dominio completo + puerto. | **`sub.manz.dev`** | **`localhost:8000`** |
| **`.origin`** | Origen (Protocolo + host) | **`https://sub.manz.dev`** | **`http://localhost:8000`** |
| **`.username`** | Nombre de usuario que ha accedido. | Vacío | **`manz`** |
| **`.password`** | Contraseña del usuario que ha accedido. | Vacío | **`12345`** |
| **`.port`** | Puerto en escucha de la web. | Vacío | **`8000`** |
| **`.pathname`** | Ruta completa (ruta + documento) | **`/path/page.html`** | **`/path/file.mp3`** |
| **`.hash`** | Ancla (lo explicamos más adelante) | **`#anchor`** | Vacío |
| **`.href`** | Esta propiedad devuelve la URL completa (query strings incluídas, ver más adelante). |  |  |

Ten en cuenta los siguientes detalles:

- La diferencia entre **`.hostname`** y **`.host`** es que el segundo incluye el **puerto** (***si está definido explícitamente***).
- El **origen** (**`origin`**) es la unión del protocolo + dominio completo + puerto (***si se indica***).

Teniendo claras las diferentes partes de una **URL**, vamos a ver ahora como podríamos trabajar con ellas y acceder a partes especificas desde nuestro código Javascript.

### [**Protocolo de la URL**](https://lenguajejs.com/javascript/peticiones-http/url/#protocolo-de-la-url)

Normalmente, a una web se accede mediante el protocolo **`http://`**, sin embargo, hoy en día está más extendido el protocolo **`https://`**, que es el mismo pero con una capa de seguridad adicional donde los datos van cifrados (***al contrario que en HTTP***).

### [**Usuario y Contraseña**](https://lenguajejs.com/javascript/peticiones-http/url/#usuario-y-contrase%C3%B1a)

Generalmente, al acceder a una web no se suele proporcionar el usuario y contraseña, pero es posible hacerlo directamente desde la URL. De hacerlo, hay que indicar el usuario después de las **`//`** del protocolo. Si queremos añadir también un password, habría que añadirlo inmediatamente después del usuario, separándolo por **`:`** y, finalmente, después del password, añadir el símbolo **`@`** para separarlo del dominio.

```jsx
"https://manz.dev/login/"             // Acceso anónimo (sin usuario ni pass)
"https://manz@manz.dev/login/"        // Acceso como usuario manz (sin pass)
"https://manz:12345@manz.dev/login/"  // Acceso como usuario manz con pass 12345
```

> **OJO**: Hoy en día, los nombres de usuario y contraseñas se suelen gestionar más frecuentemente a nivel de aplicación. En este caso hemos explicado como utilizarlos a nivel de servidor.
> 

### [**Dominio, subdominio y TLD**](https://lenguajejs.com/javascript/peticiones-http/url/#dominio-subdominio-y-tld)

Cuando hablamos de nombre de dominio, muchas veces solemos abarcar todo, es decir, en nuestro ejemplo, **`sub.manz.dev`**. Sin embargo, hay que tener en cuenta que tenemos tres partes:

- **Subdominio**: **`sub`**, una división específica del dominio
- **Dominio**: **`manz.dev`**, el dominio en cuestión
- **TLD** (***Top Level Domain***): **`.dev`**, la terminación del dominio

### [**Puerto de la URL**](https://lenguajejs.com/javascript/peticiones-http/url/#puerto-de-la-url)

Cualquier página está alojada en un servidor web y dicho servidor web debe estar continuamente escuchando peticiones para que los usuarios puedan conectarse y acceder a la web. Por norma general, los servidores web escuchan en el puerto **`80`** (HTTP) o en el puerto **`443`** (HTTPS), aunque se puede configurar un puerto diferente.

El **puerto** es un número (***del 1 al 65535***) que se debe indicar precedido del símbolo **`:`**, justo al final del dominio. En el caso de que no se indique explícitamente un número de puerto, se utilizará el puerto por defecto y no mostrará en la URL, que es el caso más habitual.

```jsx
"https://manz.dev/"       // Se accede por puerto 443 (HTTPS por defecto).
"https://manz.dev:3000/"  // Se accede por puerto 3000 explícitamente.
"https://manz.dev:443/"   // Se accede por puerto 443 (es el mismo que el caso 1)
```

### [**Ruta de la URL**](https://lenguajejs.com/javascript/peticiones-http/url/#ruta-de-la-url)

La **ruta** de una URL es la estructura de carpetas a la que vamos a acceder para descargar la página. Por defecto, si no se le indica una página o documento explícitamente, se suele buscar la página **`index.html`** o **`index.htm`**, aunque depende de la configuración.

```jsx
"https://manz.dev/streams/"           // Carpeta streams
"https://manz.dev/software/mkweb/"    // Carpeta mkweb, dentro de la carpeta software
"https://manz.dev/"                   // Carpeta principal (raíz)
```

> En frontend, en muchas ocasiones, no tenemos **rutas reales** que equivalen a carpetas, sino que trabajamos con **pseudo-rutas**, una especie de ruta artificial creada para simular las rutas reales.
> 

### [**Trailing slash (barra final)**](https://lenguajejs.com/javascript/peticiones-http/url/#trailing-slash-barra-final)

Observa que cuando indicamos una URL que termina en una ruta (***sin indicar página o documento***), muchas veces te encontrarás una **`/`** al final y otras veces no. Esta **`/`** se denomina **trailing slash**. Puede parecer la misma página, pero mucho cuidado, ya que en algunos casos pueden ser URL diferentes:

```jsx
"https://manz.dev/streams/"         // Estamos accediendo a una carpeta llamada "streams"
"https://manz.dev/streams"          // Estamos accediendo a un fichero sin extensión llamado "streams"
```

En el primer caso no hay duda, se accede a la carpeta **`streams/`**. Sin embargo, en el segundo caso, si **`streams`** es una carpeta, lo que ocurrirá es que redireccionará a **`streams/`**, lo que hará que busque **`streams/index.html`**. Pero si en lugar de una carpeta, **`streams`** es un archivo (***sin extensión***), estaríamos accediendo a ese documento.

# [**Qué es un automatizador?**](https://lenguajejs.com/javascript/automatizadores/introduccion/)

## **Empaquetadores Javascript para automatizar tareas**

Antiguamente, cuando teníamos que crear un nuevo sitio web, debíamos crear manualmente una **carpeta para el proyecto**, las diferentes subcarpetas de las secciones de la web (***imágenes, css, js, etc...***), configurar un servidor web (***se solía usar XAMPP o similares***), colocar y enlazar las diferentes librerías CSS y/o Javascript que queríamos utilizar, etc...

Aunque eso todavía se puede hacer hoy en día, los automatizadores nos ayudan a simplificar este proceso con el que podemos gastar mucho tiempo realizando **transpilaciones**.

# [**¿Qué es transpilar?**](https://lenguajejs.com/javascript/automatizadores/introduccion/#qu%C3%A9-es-transpilar)

Una transpilación es la tarea de transformar el código fuente de un lenguaje a otro código fuente diferente. En nuestro caso, los **automatizadores** leen nuestro código Javascript y lo modifican, realizando cambios para que no tengamos que hacerlo nosotros manualmente y sea mucho más cómodo utilizarlo.

Con la evolución del desarrollo web, hemos pasado a trabajar **transpilando código**. Habitualmente, trabajamos en una carpeta **`src/`** donde tenemos nuestro código fuente. Ese código se preprocesa y se traduce a otro código (***en la carpeta `dist/`***) que es el código que finalmente leerá nuestro navegador. Mantener actualizado el código fuente que escribimos con el que lee el navegador sin automatizarlo, es una tarea muy tediosa. De ahí surgen los **automatizadores**.

# [**¿Por qué transpilar?**](https://lenguajejs.com/javascript/automatizadores/introduccion/#por-qu%C3%A9-transpilar)

Actualmente, en el ecosistema **Javascript** (***o en el mundo del desarrollo web en general***), es muy común utilizar estos **automatizadores** para, entre otras cosas, agilizar el proceso de creación de una aplicación web con unos pocos comandos, realizando de forma automática todas esas tareas tediosas y repetitivas, alcanzando nuestro objetivo de forma más rápida y con una mejor experiencia de desarrollador.

Algunas de esas tareas podrían ser las siguientes:

- 1️⃣ Creación del **proyecto** y su gestión (***generalmente, con [NPM](https://lenguajejs.com/npm/)***)
- 2️⃣ Actualización y mantenimiento de **dependencias** (***generalmente, con [NPM](https://lenguajejs.com/npm/)***)
- 3️⃣ **Servidor web local** de desarrollo
- 4️⃣ **Minificación** de código
- 5️⃣ **Optimización** de imágenes
- 6️⃣ **Preprocesar** o transpilar código fuente
- 7️⃣ **Despliegue** o subida del código final al servidor

Todas estas tareas pueden ser realizadas de forma manual, pero con el uso de un automatizador, lo hacemos automáticamente, de forma más rápida y, muy probablemente, con menos errores.

> Hoy en día, los automatizadores más populares son **Vite** y **Webpack**. Si estás comenzando un desarrollo te recomiendo encarecidamente que pruebes [Vite](https://lenguajejs.com/javascript/automatizadores/vite/), ya que es el más rápido y moderno, y el que tiene más futuro.
> 

# [**Tutorial inicial de Vite**](https://lenguajejs.com/javascript/automatizadores/vite/)

## **Primeros pasos para utilizar el empaquetador ViteJS**

**Vite** se define como una herramienta de frontend que te ayudará a crear tus proyectos de forma agnóstica (***sin atarte a ningún framework concreto***) y que su desarrollo y construcción final sea lo más sencilla y cómoda posible. Está desarrollada por **Evan You**, el creador de [Vue](https://lenguajejs.com/vuejs/).

Actualmente, **Vite** soporta la creación tanto de proyectos vanilla (***sin utilizar frameworks***), como proyectos utilizando **Vue**, **React**, **Preact**, **Svelte** o **Lit** (***tanto usando Javascript como Typescript***).

# [**Crear un proyecto con Vite**](https://lenguajejs.com/javascript/automatizadores/vite/#crear-un-proyecto-con-vite)

Para comenzar, simplemente necesitamos tener instalado **NodeJS**. Utilizaremos **`npm`** para comenzar el proyecto. Escribimos desde una terminal:

```bash
$ npm create vite demo-project

Need to install the following packages:
  create-vite
Ok to proceed? (y) y
```

El comando **`npm create vite`** hará toda la magia por nosotros. En nuestro ejemplo, **`demo-project`** sería el nombre de la carpeta del proyecto, por lo que este comando ya se encargará de crear la carpeta, ni siquiera tendremos que crearla nosotros.

Se nos advertirá que es necesario instalar el paquete **`create-vite`** de no tenerlo instalado, que es el asistente encargado de crear la aplicación web. Al responder afirmativamente, nos aparecerá un menú para seleccionar que plantilla queremos utilizar (***al elegir una, luego nos preguntará si queremos la versión javascript o typescript***).

# [**Plantillas de Vite**](https://lenguajejs.com/javascript/automatizadores/vite/#plantillas-de-vite)

Si no queremos que nos aparezca ese menú interactivo, es posible indicar un parámetro opcional **`--template`** para especificar directamente la plantilla a utilizar sin que nos salte el asistente:

```bash
$ npm create vite demo-project -- --template vanilla
```

Las plantillas que tenemos disponibles en **`Vite`** son las siguientes (***son las que se establecen al elegir las opciones en el menú***):

| **Plantilla** | **Descripción** | **URL** |
| --- | --- | --- |
| **`vanilla`** | Proyecto vanilla, sin frameworks. Versión Javascript y Typescript. | [vanilla](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-vanilla) [vanilla-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-vanilla-ts) |
| **`vue`** | Proyecto con el framework Vue. Versión Javascript y Typescript. | [vue](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-vue) [vue-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-vue-ts) |
| **`react`** | Proyecto con la librería React. Versión Javascript y Typescript. | [react](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react) [react-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) |
| **`preact`** | Proyecto con la librería Preact. Versión Javascript y Typescript. | [preact](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-preact) [preact-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-preact-ts) |
| **`lit`** | Proyecto con la librería Lit. Versión Javascript y Typescript. | [lit](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-lit) [lit-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-lit-ts) |
| **`svelte`** | Proyecto con la librería Svelte. Versión Javascript y Typescript. | [svelte](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-svelte) [svelte-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-svelte-ts) |

Una vez hecho el proceso, comprobaremos que la tarea de creación del proyecto es prácticamente instantánea. Esto ocurre así porque **Vite** no realiza el proceso de instalación de paquetes automáticamente, por lo que tendremos que hacerlos nosotros manualmente de forma posterior:

```bash
$ cd demo-project
$ npm install
```

Con esto ya tendremos el proyecto listo para arrancarlo con el script **`npm run dev`** y comenzar a desarrollar. Ten en cuenta que en todos los proyectos que generes tendrás un script **`dev`** que lanza el **modo de desarrollo de Vite** y, por otro lado, tendrás un script **`build`** que lanza el **modo de producción de Vite**, que es el que genera la subida en la carpeta **`dist`**, que es la que irá a producción.

# [**El fichero vite.config.js**](https://lenguajejs.com/javascript/automatizadores/vite/#el-fichero-viteconfigjs)

En los proyectos de **Vite** encontrarás un fichero **`vite.config.js`**. Se trata de un fichero de configuración donde puedes establecer algunos detalles del funcionamiento del empaquetador en el proyecto actual. La estructura general de este fichero es la siguiente:

```jsx
import { defineConfig } from "vite";

export default defineConfig({
  root: "./",
  base: "/",
  publicDir: "public",
  build: {
    outDir: "dist",
    assetsDir: "assets"
  },
  plugins: []
});
```

Dependiendo de la plantilla utilizada, este fichero de configuración puede ser diferente o incluso no existir (***como es en el caso de los proyectos de Javascript vanilla***).

# [**Temporizadores**](https://lenguajejs.com/javascript/web-apis/temporizadores/)

Los **temporizadores** (***timers***) son funciones especiales que permiten ejecutar una función que realice ciertas tareas después de un determinado tiempo. Por un lado, los temporizadores **timeout** ejecutan cuando pasa un cierto tiempo, mientras que los temporizadores **interval** se ejecutan constantemente cada cierto tiempo.

# [**La función `setTimeout()`**](https://lenguajejs.com/javascript/web-apis/temporizadores/#la-funci%C3%B3n-settimeout)

La función **`setTimeout(f, ms)`** nos pide dos parámetros: la  función **`f`** a ejecutar y el  tiempo **`ms`** que debemos esperar antes de que se ejecute (***en milisegundos***).

```jsx
console.log("Ejecución 1");

function action() {
  console.log("Ejecución 2");
}

setTimeout(action, 5000);
```

Si ejecutas este fragmento de código, comprobarás que aparece el mensaje **`Ejecución 1`** y a los **5 segundos** aparecerá **`Ejecución 2`**. Observa que hemos declarado la función **`action()`** antes de ejecutar el **`setTimeout()`**, al cuál se lo pasamos por parámetro.

 como una [función flecha](https://lenguajejs.com/javascript/introduccion/funciones/#arrow-functions) es mucho más cómodo a la hora de escribirla, ya que nos ahorramos líneas y se puede escribir de forma más compacta:

```jsx
console.log("Ejecución 1");

setTimeout(() => console.log("Ejecución 2"), 5000);
```

> Ten en cuenta que los navegadores poseen múltiples excepciones (incluso particulares, por cada navegador), por las que el temporizador podría no ser preciso en favor de no sacrificar el rendimiento del navegador.
> 

# [**La función `setInterval()`**](https://lenguajejs.com/javascript/web-apis/temporizadores/#la-funci%C3%B3n-setinterval)

Como puedes ver, **`setTimeout()`** no es el único temporizador. La función **`setInterval()`** ejecuta una función **cada cierto tiempo**. Como vimos anteriormente, **`setTimeout()`** espera el número indicado de segundos para ejecutar la función proporcionada por parámetro, y una vez ejecutada termina el temporizador.

Por otro lado, la función **`setInterval()`** espera el número indicado de segundos y ejecuta la función proporcionada, una vez hecho, vuelve a repetir el proceso una y otra vez:

```jsx
setInterval(() => console.log("Bart y Lisa: Papá, ¿hemos llegado ya?"), 3000);
```

Como puedes ver, esta función se ejecutará cada 3 segundos, continuamente.

> Ten mucho cuidado al colocar temporizadores dentro de un setInterval(). En el caso de incluir un setTimeout() podría no ser grave, pero en el caso de añadir un setInterval() dentro de otro, podrías provocar una bomba fork.
> 

La **bomba fork** (o **fork bomb**) es un tipo de ataque de denegación de servicio (DoS) que explota la capacidad de un sistema operativo para crear nuevos procesos. Consiste en un programa que se replica a sí mismo indefinidamente, consumiendo rápidamente los recursos del sistema (CPU, RAM y procesos disponibles) hasta que la computadora se vuelve inusable o se bloquea.

# [**Detener temporizadores**](https://lenguajejs.com/javascript/web-apis/temporizadores/#detener-temporizadores)

Aunque no lo hemos mencionado anteriormente, tanto el temporizadores **`setTimeout()`** como **`setInterval()`** devuelven un  número al ejecutarse. Este número es un identificador único del temporizador. Es útil cuando queremos detener prematuramente el temporizador y cancelar inmediatamente la ejecución del mismo.

Por ejemplo, observa este ejemplo de **`clearTimeout()`** en un temporizador **`setTimeout()`**:

```jsx
console.log("Inicio del código");

const id = setTimeout(() => console.log("EJECUTADO!"), 5000);
clearTimeout(id);
```

En este caso, el **`console.log()`** de **`EJECUTADO!`** nunca será mostrado por consola, ya que al programarlo para **dentro de 5 segundos**, inmediatamente después es cancelado con la función **`clearTimeout()`**, a la cuál le proporcionamos el identificador que guardamos en **`id`** en la línea anterior.

Ocurre exactamente igual en el caso del **`setInterval()`**:

```jsx
console.log("Inicio del código");

const id = setInterval(() => console.log("Mensaje que saldrá cada segundo"), 1000);
```

Una vez se ejecute este fragmento de código, veremos que se muestra en consola varios mensajes por cada segundo. Una vez ejecutemos la línea de código **`clearInterval(id)`**, ese temporizador se detendrá, y por lo tanto, no se verá más el mensaje.

# [**Usando `requestAnimationFrame()`**](https://lenguajejs.com/javascript/web-apis/temporizadores/#usando-requestanimationframe)

En temáticas de desarrollo de juegos, o a la hora de mostrar animaciones, muchas veces es necesario crear un bucle **`loop`**, que se vaya llamando continuamente y mostrando los cambios de la animación, personaje o elementos del videojuego, por ejemplo. Para ello, hay que llamar al bucle un número específico de veces cada cierto tiempo.

Si lo llamamos muy pocas veces, la animación será lenta o irá a golpes, si la llamamos demasiadas veces, estaremos trabajando de más y podríamos tener un problema de rendimiento.

> Se suele decir que el número de frames apropiado por segundo es 60, es decir, 1000 / 60, o lo que es lo mismo, aproximadamente 16 ms. Esto hace que la animación sea fluida y se vea correctamente.
> 

Esto traducido a **`setTimeout()`** sería lo siguiente:

js

```jsx
const FPS = 1000 / 16;

const loop = () => {
  console.log("Tick... Tack...");
  setTimeout(loop, FPS);
}

setTimeout(loop, FPS);
```

Sin embargo, tenemos una alternativa a **`setTimeout()`** especialmente orientada a animaciones, denominada **`requestAnimationFrame()`**. Observa que funciona de forma muy parecida, sólo que no es necesario indicarle el número de FPS, ya que lo calcula automáticamente.

Esto es una de las ventajas de esta función respecto a **`setTimeout()`**. La cantidad de FPS no siempre debe ser constante, sino que en algunos momentos del bucle puede variar y necesitar más o menos cantidad. Por lo tanto, en el caso del **`setTimeout()`** tendríamos que estar cambiando ese valor, y no resulta práctico.

Sin embargo, **`requestAnimationFrame()`** lo calcula por si mismo, y sólo vuelve a ejecutar el bucle cuando es el momento oportuno. Esto hace que las animaciones sean muy fluidas y no se utilice tiempo extra o insuficiente, mientras que el programador no debe preocuparse de realizar los cálculos:

```jsx
const loop = () => {
  console.log("Tick... Tack...");
  requestAnimationFrame(loop);
}

requestAnimationFrame(loop);
```

Una forma de comprobar la utilidad de este **`requestAnimationFrame()`** sobre el tradicional **`setTimeout()`** es si ejecutamos el bucle y cambiamos a otra pestaña. En el caso de **`setTimeout()`** el bucle se seguirá ejecutando aunque tengamos la página minimizada y no estemos viendo nada, lo que probablemente estaría desperdiciando recursos, batería, etc..

Por otro lado, en el caso de **`requestAnimationFrame()`** se podrá comprobar que el **`console.log()`** se detiene, y sólo se ejecuta cuando el usuario tiene la pestaña o ventana activa y la está mostrando.

> Desde hace algunas versiones (2021), los navegadores han establecido un sistema de control para los temporizadores y pueden estar limitados si el navegador lo consideran oportuno. [ Más info ]
> 

De la misma forma que **`setTimeout()`** y **`setInterval()`**, esta función tiene su propia función para cancelar el temporizador optimizado, que se denomina **`cancelAnimationFrame()`**. De la misma forma, también se le tiene que pasar el **`id`** que devuelve **`requestAnimationFrame()`**.

# [**LocalStorage y SessionStorage**](https://lenguajejs.com/javascript/web-apis/localstorage/)

## **Almacenamiento persistente de datos en el navegador**

Una de las limitaciones que podemos tener en Javascript cliente (***navegador***) es que a priori no es posible guardar de forma **persistente** nuestros datos, de forma que cuando recargues la página, continue conservando esos datos. Sin embargo, existe un mecanismo de navegador llamado **LocalStorage** que permite hacer algo similar: guardar los datos que le indiquemos en el propio navegador del usuario, de modo que posteriormente pueda recuperarlos.

# [**¿Qué es el LocalStorage?**](https://lenguajejs.com/javascript/web-apis/localstorage/#qu%C3%A9-es-el-localstorage)

El **LocalStorage**, como su propio nombre indica, es un almacén que permite guardar datos de forma local, en nuestro navegador. Esto es importante porque hay que tener en cuenta que los datos sólo serán accesibles por el usuario que los ha guardado, y en el navegador que lo ha hecho, ya que se almacenan ahí.

Algunos datos importante sobre el almacenamiento de datos:

- 1️⃣ Cada dato guardado se identifica con un nombre, que será un .
- 2️⃣ Los valores se guardan siempre como . Si tienes objetos o arrays, [pasalos a JSON](https://lenguajejs.com/javascript/objetos/json/#c%C3%B3mo-utilizar-json).
- 3️⃣ Los datos se guardan por **dominio**. Desde un dominio diferente no puedes recuperar esos datos.
- 4️⃣ Si utilizas otro **navegador**, no tendrás los datos, ya que se guardan en el navegador. Puedes verlos desde el **Dev Tools**, en la pestaña **Applications**, sección **LocalStorage**.

El objeto **`localStorage`** tiene los siguientes métodos, que podemos escribir en nuestro código:

| **Método o propiedad** | **Descripción** |
| --- | --- |
| **`length`** | Devuelve la cantidad de elementos de datos almacenados en la página actual. |
| **`getItem(key)`** | Devuelve la información asociada al dato con nombre **`key`**. |
| **`setItem(key, value)`** | Guarda el valor **`value`** en el dato con nombre **`key`**. |
| **`removeItem(key)`** | Elimina el dato guardado con el nombre **`key`**. |
| **`key(number)`** | Muestra la key del elemento guardado en la posición **`number`** del localStorage. |
| **`clear()`** | Vacía todos los datos del almacén del localStorage para esta página. |

Mediante estos métodos podemos acceder a los datos del localStorage. Veamos como funcionan.

# [**Obtener o guardar datos**](https://lenguajejs.com/javascript/web-apis/localstorage/#obtener-o-guardar-datos)

Para obtener o guardar datos en el **localStorage**, simplemente debemos utilizar los métodos **`getItem()`** o **`setItem()`** con la información correspondiente:

```jsx
localStorage.length;  // 8 (Datos en el localStorage)
localStorage.setItem("username", "ManzDev"); // Guardamos

const username = localStorage.getItem("username");  // Recuperamos
localStorage.removeItem("username");  // Eliminamos

console.log(username);  // "ManzDev"
```

Existe una forma rápida de guardar y obtener datos en el localStorage. En lugar de utilizar los métodos anteriores, podemos hacer referencia directamente a la propiedad concreta que queremos obtener o guardar:

```jsx
localStorage.username = "ManzDev";    // Equivale a .setItem()
localStorage.username;                // Equivale a .getItem()
```

# [**Obtener todos los datos guardados**](https://lenguajejs.com/javascript/web-apis/localstorage/#obtener-todos-los-datos-guardados)

Si queremos acceder a todos los datos guardados en el **`localStorage`**, podemos hacer un bucle que revise todos los elementos con un índice. Por ejemplo, desde **`0`** hasta **`localStorage.length`** y obtenemos el nombre del dato con **`key()`** y su valor con **`getItem()`**:

```jsx
for (let i = 0; i < localStorage.length; i++) {
  const key = localStorage.key(i);
  const value = localStorage.getItem(key);
  console.log(`${key}=${value}`);
}
```

# [**Vaciar el almacén**](https://lenguajejs.com/javascript/web-apis/localstorage/#vaciar-el-almac%C3%A9n)

Aunque es menos frecuente, es posible ejecutar el método **`clear()`** para vaciar todas las keys del localStorage. Ojo, que esto sólo borra las keys para el dominio actual, no todas las que están almacenadas en el navegador. Veamos un ejemplo:

```jsx
localStorage.clear();   // Vacía todas las keys
```

# [**¿Qué es el SessionStorage?**](https://lenguajejs.com/javascript/web-apis/localstorage/#qu%C3%A9-es-el-sessionstorage)

Además del **localStorage** mencionado, tenemos otra versión similar denominada **sessionStorage**. La idea es la misma, ambos pertenecen a la **API WebStorage**, sin embargo, la diferencia principal es que **`sessionStorage`** guarda temporalmente los datos **hasta que cierras la pestaña**, mientras que **`localStorage`** los guarda y no los borra aunque cierres la pestaña del navegador.

Sin embargo, **`sessionStorage`** tiene los mismos métodos y la API se usa de la misma forma que **`localStorage`**.

# [**Características interesantes**](https://lenguajejs.com/javascript/web-apis/localstorage/#caracter%C3%ADsticas-interesantes)

Algunas características interesantes comparando **LocalStorage** y **SessionStorage**:

| **Característica** | **LocalStorage** | **SessionStorage** |
| --- | --- | --- |
| **Acceso** | En todas las pestañas del mismo dominio. | Sólo en la pestaña que se creó. |
| **Duración** | Hasta que se eliminen manualmente. | Hasta que se cierra la pestaña. |
| **Capacidad** | ~[10MB](https://developer.chrome.com/docs/extensions/reference/api/storage?hl=es-419#storage_areas) en Chrome, aunque puede variar por navegador. | Similar a localStorage. |
| **Modo incógnito** | Los datos se borran al cerrar la pestaña. | Igual a LocalStorage. |

Como curiosidad, si comparamos el localStorage/sessionStorage con las clásicas cookies, suelen ser un buen reemplazo, ya que evitan el clásico problema de enviar la cookie en cada petición web, mientras que la API de Web Storage sólo descarga los datos cuando lo solicitas desde Javascript.
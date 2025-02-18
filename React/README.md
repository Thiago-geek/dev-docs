# ¿Qué es React?
React es una librería para crear interfaces web de usuario con Javascript. El objetivo de React es tener a nuestra disposición un lenguaje que simplifique la cantidad de detalles que hay que hacer en Javascript, sin perder demasiado control o personalización en lo que hacemos.

Por esa razón, muchos de los conceptos que vamos a ver relacionados con React, cambian los fundamentos o conceptos utilizados en el desarrollo web, introduciendo nuevos conceptos o realizando muchas tareas de forma transparente por debajo, de modo que el desarrollador no tenga que controlar al detalle muchas de esas cosas.

> # OJO:
>> Que no tengas que controlar muchos de estos detalles no quiere decir que puedas >> permitirte desconocerlos. Si ignoras estos fundamentos o bases, podrás hacer 
>> cosas sencillas, pero te costará mucho dominar o trabajar con React.

# Conceptos
Antes de continuar, recuerda que React es una abstracción, es decir, un lenguaje que está sobre Javascript, y para simplificar el trabajo del desarrollador, cambia muchos patrones y formas de trabajar por otras, con el objetivo de que sea más sencillo.

Veamos una lista de conceptos que se utilizan en React como equivalencia a patrones utilizados en Javascript u otros sectores:

# 🧩 Componentes
En React se trabaja con componentes. A grandes rasgos, se trata de crear «etiquetas propias» que se comportan como etiquetas HTML. La forma preferida de crearlas es utilizar los llamados componentes funcionales, es decir, funciones de Javascript que devuelven código HTML (o casi):

```javascript
function component() {
  return <h1>¡Hola, amigo!</h1>;
}
```

# 🔥 JSX
En React se utiliza JSX como lenguaje de marcado en lugar de HTML. JSX es una sintaxis que, aunque parece HTML, realmente es Javascript y se encarga de leer el código JSX y convertirlo a un HTML equivalente con añadidos Javascript:

```
function component() {
  const name = "Manz";
  return (
    <div>
      <h1>¡Hola, {name}!</h1>
    </div>
  );
}`
```

### [**🌌 Virtual DOM**]
En el ecosistema de React no se suele trabajar directamente con el DOM. Aunque puedes hacerlo, está mal visto y se considera una mala práctica. Esto es así porque React utiliza su llamado **Virtual DOM**: una especie de DOM ligero en memoria que es al que **React** accede directamente. Por esta razón, normalmente el desarrollador de React no necesita preocuparse por el DOM. **React** se encargará de mantenerlo actualizado cuando sea necesario.

Existe un **mito** que afirma que el «**DOM es lento**» y es mejor utilizar un [Virtual DOM](https://svelte.dev/blog/virtual-dom-is-pure-overhead). 
Esto no es cierto. Realmente, el **DOM** no es lento, sino que es muy común que se gestione incorrectamente por el desarrollador. Si evitamos acceder al DOM real y dejamos esa tarea al Virtual DOM de React, evitamos la posibilidad de gestionarlo incorrectamente.

### [**🏹 Datos unidireccionales**](https://lenguajejs.com/react/introduccion/que-es-react/#datos-unidireccionales)

Al contrario de como se trabaja en otros ecosistemas, en **React** los datos viajan de forma **unidireccional**, o sea, esto significa que un elemento HTML padre puede enviar datos a sus elementos HTML hijos, pero no a la inversa.

Entenderemos esto un poco más adelante. De momento, lo que debemos tener en cuenta es que debido a esta «limitación» tenemos una ventaja y una desventaja:

- 🟩 Es más **simple** y **predecible** gestionar los datos.
- 🟥 Es menos **flexible** al no poder trabajar de forma bidireccional.

En casos donde se requiera compartir datos de forma más compleja, se suelen optar por [stores](https://lenguajejs.com/react/datos/librerias-store/) (***librerías con estado centralizado***), de las que hablaremos más adelante.

 debes tener en cuenta que, aunque **React** sea una librería de frontend, la forma habitual de utilizar **React** requiere ciertas herramientas que transpilan el código. Esto significa que el Javascript que escribes, se convierte a otro código Javascript, que es el que finalmente se lee en el navegador.

En este artículo vamos a ver los pasos que debes saber para prepararte para utilizar **React**.

# [**Requisitos**](https://lenguajejs.com/react/introduccion/instalacion/#requisitos)

- [NodeJS](https://lenguajejs.com/npm/introduccion/instalacion-node-con-pnpm/) instalado
- [NPM](https://lenguajejs.com/npm/administracion/instalar-paquetes-npm/), [pnpm](https://pnpm.io/) o un gestor de paquetes para NodeJS.
- **React** se suele usar mediante un automatizador como [Vite](https://lenguajejs.com/javascript/automatizadores/vite/), [Webpack](https://webpack.js.org/) o similar.

> En **React** lo normal es utilizar ficheros **`.jsx`** en lugar de **`.js`**. Aunque el navegador no es capaz de leer este tipo de ficheros, habíamos mencionado que React (***junto a Vite***) convierte nuestro código fuente a un código Javascript diferente, que es el que realmente lee el navegador.
> 

```jsx
export function App() {
  const name = "Manz";
  return (
    <div>
      <h1>¡Hola, {name}!</h1>
    </div>);
}
```

Observa que tras el **`return`** tenemos unos paréntesis. Aunque parece que estamos devolviendo HTML, esos paréntesis contienen **código JSX** (***una mezcla de HTML y Javascript***). 

# [**Otras formas de usar React**](https://lenguajejs.com/react/introduccion/instalacion/#otras-formas-de-usar-react)

En este tutorial estamos utilizando **React** como librería mediante un popular automatizador llamado [Vite](https://lenguajejs.com/javascript/automatizadores/vite/). Sin embargo, no es la única forma de utilizar React hoy en día.

- **Create React App**: Es posible que leas que otra forma de utilizar React es mediante **CRA** (***Create React App***). Esta es una forma antigua y desaconsejada, por lo que si encuentras una guía o te aconsejan usar CRA, lo más probable es que se trate de información desactualizada.
- **NextJS**: Una de las formas más comunes de utilizar React hoy en día es utilizando [NextJS](https://nextjs.org/). En ese caso estaríamos utilizando React como un framework, y no como una librería. Como ventaja, muchas características están automatizadas y son más sencillas, mientras que como inconveniente es que el frontend comienza a estar mezclado con backend y servicios de NextJS (***u otro proveedor***), generando cierta dependencia y acoplamiento a dichos servicios.

Cuando trabajamos con React y necesitamos escribir el HTML de un fichero o componente, no vamos a escribir HTML directamente (***aunque pueda parecer que lo estamos haciendo***). En React se utiliza una sintaxis llamada **JSX**, que realmente es código Javascript con apariencia de HTML que se escribe en el interior de funciones llamados **componentes funcionales** en los que profundizaremos un poco más adelante.

# [**¿Qué es JSX?**](https://lenguajejs.com/react/componentes/jsx/#qu%C3%A9-es-jsx)

Como hemos mencionado, **JSX** es código Javascript con apariencia de marcado HTML. Observa la siguiente función de ejemplo que devuelve un fragmento de código **JSX**:

```jsx
function component() {
  return <h1>Hola</h1>;
}
```

Si conoces minimamente Javascript, esto te resultará bastante extraño, ya que no se puede añadir una etiqueta HTML directamente en el código Javascript (***observa que no tiene las comillas de un string***). Pero como hemos mencionado, estamos trabajando con ficheros **`.jsx`** que son procesados por Vite y React antes de llegar al navegador, por lo que el Javascript final es diferente.

Para dejarlo más claro, vamos a ver que es realmente lo que le llega al navegador de ese fragmento de **código JSX**:

```
function component() {
  return <h1>Hola</h1>;
}

const jsx = component();
console.log(jsx);
```

```
/* El objeto JSX devuelto por la función */
{
  $$typeof: Symbol,
  key: null,
  props: { ... },
  _owner: FiberNode,
  _store: { ... }
}
```

React se encargará internamente de trabajar con ese objeto por nosotros y añadirlo al HTML real de la página, de modo que nosotros solo nos tengamos que preocupar del código que escribimos en el editor.

# [**HTML vs JSX**](https://lenguajejs.com/react/componentes/jsx/#html-vs-jsx)

Aunque pueda parecerlo, JSX no es 100% compatible con HTML, y tiene sus propias normas. Además, JSX permite evaluar código Javascript y devolverlo evaluado, lo que hace que sea mucho más cómodo a la hora de trabajar.

La idea es que con React podamos trabajar con lógica de programación y estructuras de datos en Javascript antes del **`return`**, y luego al devolver la información, se devuelva el código JSX para construir el HTML.

En cierta forma, la forma de pensar al trabajar con React es **crear funciones que devuelven código JSX, y que se utilizarán como si fueran una etiqueta HTML**. Veamos ahora un ejemplo donde un código HTML correcto no funcionaría en React:

```
export function App() {
  /* Aquí iría nuestra lógica Javascript */
  return (
    <div>
      <p>¡Hola, Manz! <br> ¿Qué tal estás?</p>
    </div>
  );
}
```

Este fragmento de código tiene una etiqueta HTML **`<br>`** que no requiere cierre. Esto en HTML es correcto, sin embargo, React te dará error ya que **se espera que todas las etiquetas HTML se cierren**. Hay dos formas de solucionarlo en React:

- 1️⃣ Escribir una etiqueta de cierre **`</br>`**. ❌ Correcto en React pero incorrecto en HTML puro.
- 2️⃣ «Autocerrar» la etiqueta sin cierre **`<br />`**. ✅ Válida en HTML (***heredado de XHTML***).

Lo mismo ocurre con otras etiquetas HTML que no requieren cierre como **`<img>`**, **`<hr>`**, **`<meta>`**, **`<link>`**, **`<input>`**, **`<source>`**, **`<track>`**, **`<base>`**, etc.

> Observa que cuando tenemos fragmentos JSX muy extensos, de forma opcional se puede envolver todo en paréntesis para mejorar la legibilidad.
> 

# [**Javascript en JSX**](https://lenguajejs.com/react/componentes/jsx/#javascript-en-jsx)

La **sintaxis JSX** es inteligente y nos permite añadir código Javascript de múltiples formas, adaptándose automáticamente. Dos ejemplos de ello:

- El **`name`** lo insertamos literalmente en el párrafo **`<p>`**, por lo que se genera como texto.
- El **`styles`** contiene varias propiedades CSS. JSX es lo suficientemente inteligente para entender que lo estamos asociando a [estilos en linea](https://lenguajecss.com/cascada-css/estructura/inline-styles/), por lo que lo convierte al formato que necesita por nosotros:

```
export function App() {
  const name = "Manz";
  const styles = {
    background: "indigo",
    color: "white",
    padding: "5px 15px"
  };

  return (<div style={styles}>
    <p>¡Hola, {name}!</p>
  </div>);
}
```

```
<!-- Código HTML generado -->
<div style="background:indigo;color:white;padding:5px 15px"><p>¡Hola, Manz!</p></div>
```

> **Cuidado**: Esta no es la forma adecuada de manejar estilos en React. Es sólo un ejemplo. Más adelante veremos formas adecuadas de gestionar los estilos CSS desde React.
> 

# [**Eventos JSX**](https://lenguajejs.com/react/componentes/jsx/#eventos-jsx)

Al estar utilizando Javascript junto a nuestro JSX, podemos utilizar toda la potencia de Javascript para generar nuestro HTML, y no estamos limitados a hacer algo estático. Podemos interpolar variables, usar condicionales, funciones dentro de nuestra función, bucles, eventos, etc.

> React tiene una limitación en JSX, y es que siempre debe haber un elemento padre, no pueden existir varios.
> 

# [**Fragmentos JSX**](https://lenguajejs.com/react/componentes/jsx/#fragmentos-jsx)

Es posible, que en el caso del ejemplo anterior, no queramos utilizar un elemento **`<div>`** padre porque no queremos añadir contenedores innecesarios al DOM, o porque nos complicaría el diseño CSS. En lugar de utilizar **`<div>`** podemos utilizar **fragmentos JSX**:

jsx

```
export function App() {
  /* ... */

  return (
    <>
      <button onClick={() => action("Manz")}>Click me, Manz!</button>
      <button onClick={() => action("John")}>Click me, John!</button>
    </>);
}
```

Estos símbolos **`<>`** y **`</>`** generan un HTML más compacto, sin añadir ese elemento padre **`<div>`**.

# [**Componentes funcionales**](https://lenguajejs.com/react/componentes/componentes-funcionales/)

En React existen dos formas principales de crear componentes: los **componentes de clases** y los **componentes funcionales**. Aunque se pueden utilizar ambos, en la actualidad en el ecosistema de React se prefieren los componentes funcionales porque son mucho más sencillos y directos.

# [**Ejemplos de componentes**](https://lenguajejs.com/react/componentes/componentes-funcionales/#ejemplos-de-componentes)

## Componente Funcional

Vamos a ver un ejemplo de componente muy sencillo utilizando ambas modalidades. Sin embargo, ten en cuenta que en el resto del tutorial vamos a utilizar los componentes funcionales, ya que son los que se han establecido como estándar en el ecosistema de React.

Aquí tienes un componente funcional. Se basa en construir una función, escribir su lógica en el interior (***bucles, funciones, variables, etc...***) y devolver un código JSX, que se utilizará para construir el HTML del componente:

```
function component() {
  const name = "Manz";
  return <h1>¡Hola, {name}!</h1>;
}
```

Ten en cuenta que en JSX se utiliza la sintaxis **`{variable}`** y no la sintaxis **`${variable}`** que es la que se usa en los  en Javascript nativo. Ten siempre en cuenta cuál debes utilizar.

## Componente de Clase

En el caso de los componentes de clase, observa que creamos una clase que extiende de **`Component`** o de **`React.Component`**, una clase base de React. Luego, creamos un método **`render()`** que es el que se ejecuta automáticamente para generar el HTML del componente:

```
class Component extends Component {
  render() {
    const name = "Manz";
    return <h1>¡Hola, {name}!</h1>;
  }
}
```

En él, devolvemos el código JSX que buscamos. Este tipo de componentes aunque son mucho más potentes y versátiles, se pueden complicar dependiendo de la destreza del programador.

Por esta razón, en el ecosistema de React se ha preferido apostar por los componentes funcionales, un modelo que reduce la barrera de conocimientos necesaria por parte del desarrollador, de modo que se puedan crear con una simple función.

# [**Composición**](https://lenguajejs.com/react/componentes/componentes-funcionales/#composici%C3%B3n)

Un aspecto fundamental en la programación es la **composición**. En React, es muy habitual utilizarla, de modo que debemos crear funciones (***componentes***) que se encarguen de funcionalidades específicas y si necesitamos realizar otras funcionalidades, creamos otro componente y el primero utiliza este último.

Hemos creado la función **`WelcomeUser`** y la hemos colocado en otro fichero **`.jsx`** con dicho nombre. Desde nuestro **`App.jsx`** podemos importarla y utilizarla como si fuera una etiqueta HTML. De esta forma podemos reutilizar o usar componentes en otros componentes:

```
import { WelcomeUser } from "./WelcomeUser.jsx";

export function App() {
  const title = `Mi Aplicación`;

  return (
    <>
      <h1>{title}</h1>
      <WelcomeUser />
    </>);
}
```

```
/* WelcomeUser.jsx */
export function WelcomeUser() {
  const user = "Manz";
  return <h2>¡Hola, {user}!</h2>;
}
```

Simplemente, la función **`WelcomeUser`** la movemos a otro fichero **`.jsx`** y le añadimos la palabra clave **`export`** al principio. De esta forma lo tendremos todo mejor organizado. Algunas consideraciones importantes:

- 1️⃣ Crea siempre tus ficheros de React con extensiones **`.jsx`** y no **`.js`**.
- 2️⃣ Aunque puedes usar **`export default`**, las exportaciones nombradas suelen ser más intuitivas.
- 3️⃣ En general, se intenta que las funciones tengan nombres compuestos y en PascalCase.
- 4️⃣ Como puedes ver, en React puedes «autocerrar» los componentes.

En **React**, **PascalCase** es una convención de nomenclatura en la que cada palabra de un identificador comienza con una letra mayúscula, sin espacios ni guiones.

> Recuerda que si el componente se va complicando, lo ideal es separar en varios componentes. Hazlo siempre que puedas reutilizar partes o quieras simplificar código y evitar que se complique.
> 

# [**Manejando eventos en JSX**](https://lenguajejs.com/react/componentes/eventos/)

> En React **no se deben utilizar** los **`addEventListener()`**, ya que React posee estrategias alternativas más apropiadas que simplifican la gestión de eventos, haciéndola mucho más sencilla.
> 

# [**Eventos JSX en React**](https://lenguajejs.com/react/componentes/eventos/#eventos-jsx-en-react)

Recordemos que en React no trabajamos directamente con HTML, sino que trabajamos con código JSX. En el ecosistema React se decidió crear una forma muy similar a como se controlan los eventos desde atributos HTML, pero con algunas diferencias, ya que utilizamos JSX.

En la parte de JSX crearemos un atributo **`onClick`**, exactamente igual a como se hace en HTML. En su valor, y entre llaves de JSX indicaremos el nombre de la función que queremos ejecutar, y que habremos definido previamente en el interior de nuestro componente:

jsx

```
export function Button() {

  const handleClick = () => {
    alert("¡Has pulsado el botón!");
  }

  return <button onClick={handleClick}>¡Púlsame!</button>;
}
```

Recuerda que puedes hacer esto con cualquier tipo de evento, simplemente añadiéndole **`on`** al nombre del evento y escribiéndolo en camelCase, al igual que se hace en HTML.

# [**Eventos sintéticos**](https://lenguajejs.com/react/componentes/eventos/#eventos-sint%C3%A9ticos)

¿Qué ocurre si queremos utilizar parámetros en nuestra función de gestión del evento? ¿O acceder a parámetros concretos como **`target`** o **`key`**? Veamos un ejemplo utilizando parámetros:

- 1️⃣ En el caso de necesitar información del evento, añadimos un parámetro **`ev`**
- 2️⃣ El segundo parámetro es nuestro dato, que recogemos en la función **`handleClick`**

```
export function Button() {

  const handleClick = (ev, text) => {
    alert(`¡Has pulsado el botón con el mensaje ${text}!`);
  }

  return <button onClick={(ev) => handleClick(ev, "test")}>¡Púlsame!</button>;
}
```

El objeto **`ev`** suele ser un objeto asociado al tipo de evento ocurrido. En nuestro caso, que es un evento **`click`** suele devolver un objeto **`PointerEvent`**. Sin embargo, en React, si hacemos un **`console.log(ev)`** comprobaremos que nos devuelve un **`SyntheticBaseEvent`**, algo similar a esto:

```
SyntheticBaseEvent {
  _reactName: "onClick",
  type: "click",
  nativeEvent: PointerEvent,
  target: button,
  ...
}
```

Un **evento sintético** es un **wrapper**, un objeto especial de React que envuelve el evento original (*que lo podemos encontrar en la propiedad **`nativeEvent`**). De esta forma, trabaja adaptando al ecosistema de React y nos facilita el trabajo, realizando ciertas tareas de forma automática y transparente:

- 1️⃣ React utiliza **delegación de eventos**. En lugar de crear un evento para cada elemento, crea uno «global» para todos y los gestiona manualmente. Esto hace que sea más eficiente y reduce el uso de memoria.
- 2️⃣ React no requiere usar **`removeEventListener()`** para limpiar los listeners de eventos, sino que lo hace automáticamente. Esto reduce la posibilidad de fugas de memoria y problemas de memoria con escucha de eventos.
- 3️⃣ Aunque ya no es tan relevante, React también ofrece compatibilidad con navegadores antiguos como Internet Explorer, que gestionan los eventos de forma diferente.

# [**¿Qué son las Props?**](https://lenguajejs.com/react/componentes/props/)

En el ecosistema de React (***y en muchos otros frameworks y librerías***) se le llama **Props** (***properties***) a los datos que se pasan de un componente a otro a través de los parámetros de una función. Estas **props** son unidireccionales, es decir, sólo se pueden pasar en un sentido (***desde elementos padres a hijos***).

Detalles importantes sobre las **props**:

- 1️⃣ **Inmutables**: Los hijos no pueden modificar las props recibidas.
- 2️⃣ **Personalizables**: Las props permiten personalizar componentes y hacerlos reutilizables.
- 3️⃣ **Unidireccionales**: Sólo van desde padres a hijos.

# [**Pasando props**](https://lenguajejs.com/react/componentes/props/#pasando-props)

Veamos dos ejemplos muy sencillos de un componente que pasa props a otro. Observa que en el segundo ejemplo, pasamos múltiples props, y para que sea menos verboso trabajar con ellas, desestructuramos y utilizamos directamente los valores de las props. Además, el último componente no pasa la prop **`role`**, y al igual que en Javascript, se puede añadir un valor por defecto:

```
function WelcomeUser(props) {
  return <h1>¡Hola {props.name}!</h1>;
}

export function App() {
  return (
    <>
      <WelcomeUser name="Manz" />
      <WelcomeUser name="Blur" />
    </>);
}
```

```
function WelcomeUser({ name, role = "viewer" }) {
  return <h1>¡Hola {name} ({role})!</h1>;
}

export function App() {
  return (
    <>
      <WelcomeUser name="Manz" role="streamer" />
      <WelcomeUser name="Blur" role="moderator" />
      <WelcomeUser name="JoseLuis" />
    </>);
}
```

**Importante**: Recuerda que las props son para datos que no cambian (***inmutables***). Estos datos no se pueden modificar desde el interior del componente que recibe dichas props. Más adelante veremos como gestionar los datos que mutan o cambian, que se denominan **Estado**.

En HTML, las etiquetas sólo pueden enviar strings a través de los atributos. Sin embargo, recuerda que en React no escribimos HTML, sino JSX, que si permite enviar estructuras más complejas por props, como por ejemplo objetos:

```
export function App() {
  return (
    <>
      <WelcomeUser user={{ name: "Anonymous", id: Math.floor(Math.random() * 256) }} />
    </>);
}
```

En este caso la prop **`user`** contiene un objeto con dos propiedades: el  **`name`** y el **`id`**. Aún así, es conveniente intentar mantener simples las props que se envían a los componentes.

# [**La prop `children`**](https://lenguajejs.com/react/componentes/props/#la-prop-children)

Observa que en los ejemplos anteriores hemos autocerrado nuestro componente **`<WelcomeUser />`**. Esto significa que la etiqueta no tiene más etiquetas anidadas en su interior. Sin embargo, es posible no utilizar el autocierre y anidar etiquetas y/o contenido.

Observa el siguiente ejemplo. En la desestructuración hemos añadido la prop especial **`children`**, que no es un atributo definido como **`name`**, sino que es una prop especial que será el elemento hijo de nuestro componente.

En este caso, en el interior del componente sólo tenemos un **`<img>`**, por lo que **`children`** será dicho elemento y tras el **`<h1>`** aparecerá la imagen:

```
function WelcomeUser({ name, children }) {
  return (
    <>
      <h1>¡Hola {name}!</h1>
      {children}
    </>);
}

export function App() {
  return (
    <>
      <WelcomeUser name="Manz">
        <img src="/assets/images/manzdev-hover.webp" alt="ManzDev" />
      </WelcomeUser>
    </>);
}
```

Sin embargo, también puede ocurrir que tengamos un caso donde existan múltiples etiquetas en el interior del componente. En este caso, **`children`** será un  y podremos hacer referencia a cada uno de los elementos hijos.

Observa este ejemplo, donde desestructuramos **`children`** y sacamos del array la **`<img>`** y el **`<p>`** para hacer referencia a ellas más cómodamente:

```
function WelcomeUser({ name, children }) {
  const [image, paragraph] = children;
  return (
    <>
      <h1>¡Hola {name}!</h1>
      {paragraph}
      {image}
    </>);
}

export function App() {
  return (
    <>
      <WelcomeUser name="Manz">
        <img src="/images/manzdev.webp" alt="ManzDev" />
        <p>Esto es un avatar de <strong>ManzDev</strong>.</p>
      </WelcomeUser>
    </>);
}
```

Con esto, ya hemos visto como acceder a información a través de **props** y al contenido del componente a través de **`children`**. Más adelante, continuaremos profundizando en más detalles relacionados con estos temas.

# [**Propagación de props**](https://lenguajejs.com/react/componentes/props/#propagaci%C3%B3n-de-props)

Cuando vamos creando componentes, muchas veces creamos gran cantidad de props y es tendioso y repetitivo referenciarlas una a una. Para solucionarlo, podemos utilizar la llamada **propagación de props**. Observa el componente **`WelcomeUser`** y como le pasamos las props a **`DataInfo`**:

jsx

```
function DataInfo({ name, role, color, image }) {
  return (
    <div style={{ background: color }}>
      <h1>{name}</h1>
      <h2>{role}</h2>
      <img src={image} alt={name} />
    </div >);
}

function WelcomeUser(props) {
  const { name } = props;
  return (
    <>
      <h1>¡Hola {name}!</h1>
      <DataInfo {...props} />
    </>);
}

export function App() {
  return (
    <>
      <WelcomeUsername="Manz"role="streamer"color="indigo"image="manzdev.webp"/>
    </>);
}
```

El componente **`<WelcomeUser>`** le está enviando todas sus props al componente **`<DataInfo />`**, pero en lugar de definirlas una por una, simplemente escribimos **`{...props}`**, desestructurando las props y referenciandolas todas.

# [**¿Qué son los Hooks?**](https://lenguajejs.com/react/componentes/hooks/#qu%C3%A9-son-los-hooks)

Los **hooks** son funciones especiales (***que empiezan siempre por `use`***) que permiten realizar tareas concretas dentro del ecosistema de **React**. Existen muchos hooks, muchos de ellos integrados en **React**, pero también es posible crear nuestros propios hooks personalizados.

Los objetivos que persiguen los hooks son los siguientes:

- 1️⃣ **Simplificar** la complejidad y conseguir componentes más sencillos
- 2️⃣ **Reutilizar** lógica Javascript y su estado (***información que cambia***)
- 3️⃣ **Organizar** mejor nuestro código y escribir menos líneas

# [**Reglas fundamentales**](https://lenguajejs.com/react/componentes/hooks/#reglas-fundamentales)

Los **hooks** de React tienen algunas reglas principales que hay que cumplir:

- 1️⃣ Los hooks se llaman en el **nivel superior**. Nunca en condicionales, bucles o funciones anidadas.
- 2️⃣ Sólo se pueden llamar en componentes funcionales o hooks. Nunca en funciones normales de Javascript.

# [**El hook `useState`**](https://lenguajejs.com/react/componentes/hooks/#el-hook-usestate)

Probablemente, el hook más sencillo de mostrar como ejemplo sea **`useState`**. Aunque lo explicaremos más adelante, vamos a ver una pequeña demostración de código donde se vea como funciona este hook.

El hook **`useState`** permite añadir y gestionar **un estado** en componentes funcionales, algo que sólo era posible antiguamente con las clases de Javascript. Si el concepto **estado** es nuevo para ti, cuando hablamos de estado nos referimos a la información que cambia en un componente.

El ejemplo más clásico de estado es la creación de un contador, que contiene un estado (***que cambia***) que es el número del contador. Veamos un ejemplo de código:

```
function Counter() {
  const [counter, setCounter] = useState(0);

  return (
    <div>
      <p>El contador está en: {counter}</p>
      <button onClick={() => setCounter(counter + 1)}>Aumentar</button>
    </div>);
}
```

El código es bastante sencillo. Observa que en el interior del componente tenemos una primera línea donde usamos el hook **`useState`**. Luego, más adelante, devolvemos un bloque **JSX** donde utilizamos tanto **`counter`** como **`setCounter`**. Vamos a explicar antes la primera parte.

Recordemos que los hooks son simplemente funciones. En la primera línea estamos ejecutando el hook **`useState()`** y nos devuelve un array con dos elementos, que estamos [desestructurando](https://lenguajejs.com/javascript/arrays/desestructuracion-arrays/) para tenerlo en dos variables separadas.

- 1️⃣ El primer elemento lo hemos llamado **`counter`** y es la información actual del contador, el estado.
- 2️⃣ El segundo elemento lo hemos llamado **`setCounter`** y es una función para actualizar ese estado.

> Por norma general, los hooks useState utilizan esta forma de nombrar, donde el segundo elemento suele comenzar por set, seguido del nombre del primer elemento, utilizando camelCase.
> 

Además, observa que el hook **`useState()`** se usa pasando el valor **`0`** por parámetro. Este valor es el **estado inicial** de nuestro counter. Ahora que tenemos claro esto, podemos entender mejor el uso de **`counter`** y **`setCounter`** en la parte del JSX.

# [**Otros hooks**](https://lenguajejs.com/react/componentes/hooks/#otros-hooks)

Aquí tienes una lista de varios hooks populares en el ecosistema de **React**:

| **Nombre** | **Descripción** | **Más info** |
| --- | --- | --- |
| **`useState`** | Crea un estado mutable y proporciona acceso para mostrarlo o modificarlo. | [Ver estado](https://lenguajejs.com/react/datos/estado/) |
| **`useEffect`** | Ejecuta lógica de forma automática después de que el DOM (UI) haya cambiado. | [Ver efectos](https://lenguajejs.com/react/componentes/useeffect/) |
| **`useContext`** | Accede a un valor compartido desde cualquier parte del código. | [Ver contexto](https://lenguajejs.com/react/datos/context-api/) |
| **`useRef`** | Crea una referencia mutable que mantenga el valor o permita acceder al DOM. | [Ver acceso al DOM](https://lenguajejs.com/react/datos/useref/) |
| **`useReducer`** | Permite manejar valores que cambian según diferentes accciones. |  |
| **`useCallback`** | Memoriza (cachea) funciones para evitar volverlas a crear. |  |
| **`useMemo`** | Memoriza (cachea) valores calculados para no recalcularlos si sus datos no han cambiado. |  |
| **`useLayoutEffect`** | Como **`useEffect`**, pero ejecutandolo después de actualizar el DOM y antes de verlo en pantalla. |  |
| **`useDebugValue`** | Muestra información útil en la consola o Dev Tools. |  |
| **`useId`** | Genera un identificador único inmutable entre renderizados. |  |
| **`useTransition`** | Asegura que las acciones lentas no bloqueen las rápidas mientras se ejecutan. |  |
| **`useDeferredValue`** | Retrasa la actualización de un valor hasta que el navegador tenga tiempo libre. |  |

# [**Efectos secundarios en React**](https://lenguajejs.com/react/componentes/useeffect/)

En React, los **efectos secundarios** se gestionan mediante el hook **`useEffect`**, pero antes de empezar a trabajar con ellos necesitamos entender sus bases. En programación, llamamos **efecto secundario** (***o side-effect***) a cualquier acción que realiza nuestro código (***en el interior de una función, por ejemplo***) y afecta a algo que se encuentra fuera del ámbito de esa función, es decir, que estamos alterando algo no relacionado directamente con lo que devolvemos en la función.

# [**Efectos secundarios**](https://lenguajejs.com/react/componentes/useeffect/#efectos-secundarios)

Para entender mejor el concepto de **efecto secundario** de la programación, imaginemos esta sencilla función de un **contador**:

```
let counter = 0;

function incrementCounter() {
  counter++; // Modifica la variable global (efecto secundario)
}

incrementCounter();
console.log(counter); // 1
```

Dicha función está alterando el valor de **`counter`**, el cuál no pertenece a la función **`incrementCounter()`**, por lo que aunque está realizando nuestro objetivo correctamente (***incrementar el contador***), se está realizando mediante un **efecto secundario**.

Algunos ejemplos comunes de efectos secundarios en JavaScript podrían ser:

- Modificar variables fuera del ámbito de su función (***ej: variables globales***)
- Realizar una operación de entrada/salida (***ej: escribir en un archivo, petición a una API...***)
- Actualizar y modificar elementos del DOM (***ej: cambios en la estructura de la página***)
- Crear temporizadores (***ej: setTimeout o setInterval***)
- Suscribirse a eventos (***ej: escuchar un click u otra acción***)

# [**Funciones puras**](https://lenguajejs.com/react/componentes/useeffect/#funciones-puras)

El ejemplo anterior se puede reeescribir intentando que tus funciones sean **puras**. Una **función pura** es una función que cumple estas condiciones:

- 1️⃣ Dado un argumento por parámetro, siempre devuelve el mismo resultado (***es determinista***).
- 2️⃣ No muta nada fuera de su ámbito (***no tiene efectos secundarios***).

Veamos el ejemplo anterior, cambiando la función **`incrementCounter()`** para que sea una función pura, y evitando la creación de efectos secundarios:

js

```
let counter = 0;

function incrementCounter(counter) {
  return counter + 1;
}

counter = incrementCounter(counter);
console.log(counter); // 1
```

Observa que en lugar de mutar la variable externa **`counter`** en la función, lo que hacemos es devolver una versión modificada de los datos que recibimos. Esto ayuda considerablemente a no crear efectos secundarios y a que nuestro código sea más predecible y evitemos bugs accidentales.

# [**Side effects en React**](https://lenguajejs.com/react/componentes/useeffect/#side-effects-en-react)

En el ecosistema de **React**, el concepto **efecto secundario** (***muchas veces abreviado como efecto***) aparece mucho y también se suele relacionar con las acciones **que tienen consecuencias fuera de la función o componente en la que se ejecuta**.

En ReactLand™ se tiende a evitar los efectos secundarios en las funciones o componentes siempre que sea posible, ya que no encajan bien con la filosofía de React:

- 1️⃣ React renderiza la UI cuando cambia el estado (***predecible***). Los efectos no son predecibles.
- 2️⃣ Efectos innecesarios pueden impactar negativamente en el rendimiento.
- 3️⃣ Los efectos secundarios descontrolados son dificiles de depurar y testear.

Sin embargo, a pesar de estas dificultades, los efectos secundarios son a menudo inevitables para construir una aplicación. Para ello, existe el hook **`useEffect`**, una herramienta para manejarlos.

# [**El hook `useEffect`**](https://lenguajejs.com/react/componentes/useeffect/#el-hook-useeffect)

En React, existe un hook llamado **`useEffect`** que sirve para gestionar efectos secundarios de forma controlada, predecible y eficiente. Primero, analicemos la estructura de un **`useEffect()`** para conocer las partes clave de este hook:

```
useEffect(() => {
  /* Montaje */

  return () => { /* Desmontaje */ }
}, [/* dependencias */]);
```

- 1️⃣ El **`useEffect()`** tiene dos parámetros: la función (***de montaje***) y las dependencias.
- 2️⃣ La función del **`useEffect`** se ejecuta cuando se monta el componente
- 3️⃣ El array **`deps`** indica las dependencias del **`useEffect`**
- 4️⃣ La función devuelta por el **`return`** se ejecuta cuando se desmonta el componente

La parte más importante aquí probablemente sea el **array de dependencias**, así que vamos a explicarlo primero. Las situaciones son las siguientes:

| **Dependencias** | **Descripción** | **Montaje** | **En cada renderizado** |
| --- | --- | --- | --- |
| **`[]`** | Sólo se ejecuta la primera vez (*montaje*). | ✅ | ❌ |
| **`[dep1]`** | Se ejecuta primera vez y al cambiar. | ✅ | 🟨 Cuando cambia **`dep1`** |
| **`[dep1, dep2]`** | Se ejecuta primera vez y al cambiar. | ✅ | 🟨 Cuando cambian **`dep1`** y/o **`dep2`** |
| *Sin array de dependencias* | Se ejecuta primera vez y en cada renderizado. | ✅ | ✅ Siempre |

Con esto claro, veamos ahora un código real utilizando un **`useEffect`**. Vamos a crear un [temporizador](https://lenguajejs.com/javascript/web-apis/temporizadores/) que se ejecutará cada segundo para mostrar la hora actual.

Al inicio del componente **`Clock`** creamos un estado **`time`** con la hora actual. Luego, creamos un **`useEffect`** con un array de dependencias vacío, por lo que se ejecutará solo la primera vez que se monta el componente:

jsx

```
import { useState, useEffect } from "react";

export function Clock() {
  const [time, setTime] = useState(new Date().toLocaleTimeString());

  useEffect(() => {
    const interval = setInterval(() => {
      setTime(new Date().toLocaleTimeString());
    }, 1000);

    return () => clearInterval(interval);
  }, []);

  return <h1>Hora actual: {time}</h1>;
}
```

En dicho **`useEffect`** creamos el **`setInterval`** cada 1 segundo (***1000ms***) y mutamos el estado **`time`** para cambiar la hora actual.

Por último, en el **`return`** devolvemos una función que se ejecutará cuando se desmonte el componente, donde es necesario realizar tareas de limpieza para evitar **fugas de memoria** o problemas similares.

> De esta forma puedes gestionar los efectos secundarios en tus componentes de React de forma controlada. Aunque es un sistema muy potente, ten mucho cuidado y no abuses de useEffect ya que puede complicar la lógica, impactar en el rendimiento y muchas veces se puede buscar una alternativa sin efectos secundarios.
>
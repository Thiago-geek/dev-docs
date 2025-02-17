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


````javascript
function component() {
  const name = "Manz";
  return (
    <div>
      <h1>¡Hola, {name}!</h1>
    </div>
  );
}
```

### [**🌌 Virtual DOM**](https://lenguajejs.com/react/introduccion/que-es-react/#virtual-dom)

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

```jsx
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

```jsx
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

```jsx
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

```html
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

```jsx
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

```jsx
function component() {
  const name = "Manz";
  return <h1>¡Hola, {name}!</h1>;
}
```

Ten en cuenta que en JSX se utiliza la sintaxis **`{variable}`** y no la sintaxis **`${variable}`** que es la que se usa en los  en Javascript nativo. Ten siempre en cuenta cuál debes utilizar.

## Componente de Clase

En el caso de los componentes de clase, observa que creamos una clase que extiende de **`Component`** o de **`React.Component`**, una clase base de React. Luego, creamos un método **`render()`** que es el que se ejecuta automáticamente para generar el HTML del componente:

```jsx
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

```jsx
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

```jsx
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

```jsx
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

```jsx
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
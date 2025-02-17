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
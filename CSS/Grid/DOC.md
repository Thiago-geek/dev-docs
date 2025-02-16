# Grid

Para activar la cuadrícula **grid** hay que utilizar sobre el elemento contenedor la propiedad **`display`** y especificar uno de los dos valores que queramos utilizar: **grid** o **inline-grid**.

| **Tipo de elemento** | **Descripción** |
| --- | --- |
| **`inline-grid`** | Establece una cuadrícula con ítems **en línea**, de forma equivalente a **`inline-block`**. |
| **`grid`** | Establece una cuadrícula con ítems **en bloque**, de forma equivalente a **`block`**. |

- `grid`**bloque**
    (se extiende en toda la línea).
    
- `inline-grid`**en línea**
    está (solo ocupa lo necesario y deja espacio para otros elementos en la misma línea).

Este valor influye en como se comportará la cuadrícula con el contenido exterior. El primero de ellos permite que la cuadrícula aparezca encima/debajo del contenido exterior (***en bloque***) y el segundo de ellos permite que la cuadrícula aparezca a la izquierda/derecha (***en línea***) del contenido exterior (***ojo, la cuadrícula entera, no cada uno de sus ítems***):

# [**Definir filas y columnas**](https://lenguajecss.com/css/grid/que-es-grid/#definir-filas-y-columnas)

### [**Filas y columnas fijas**](https://lenguajecss.com/css/grid/que-es-grid/#filas-y-columnas-fijas)

En **Grid CSS**, la forma principal de definir una cuadrícula es indicar el tamaño de sus filas y sus columnas de forma explícita. Para ello, sólo tenemos que usar las propiedades CSS **`grid-template-columns`** y **`grid-template-rows`**:

| **Propiedad** | **Valor** | **Descripción** |
| --- | --- | --- |
| **`grid-template-columns`** | [*col1*] [*col2*] ... | Establece el  SIZE de cada columna (*col 1, col 2...*). |
| **`grid-template-rows`** | [*fila1*] [*fila2*] ... | Establece el SIZE  de cada fila (*fila 1, fila 2...*). |

mediante las propiedades **`grid-template-columns`** y **`grid-template-rows`** definimos los tamaños de las columnas y las filas del mismo.

Ahora, ten en cuenta que corre de nuestra cuenta vigilar que el número de elementos hijos en el grid es el que debería. Dependiendo del número de **elementos hijos** que tenga definido el contenedor **grid** en su HTML, tendremos una cuadrícula de 2x2 elementos (***4 ítems***), 2x3 elementos (***6 ítems***), 2x4 elementos (***8 ítems***) y así sucesivamente. Incluso, si el número de ítems es impar (***por ejemplo, 5 ítems***), la última celda de la cuadrícula se quedaría vacía.

A medida que fueramos incluyendo más ítems en el grid, podríamos aumentar también el número de parámetros de la propiedad **`grid-template-columns`** y/o la propiedad **`grid-template-rows`**. En caso de tener más ítems de lo que se indica en la propiedad, los ítems restantes se incluirían sin formato. De tener menos, simplemente se ocuparían los ítems implicados.

### [**Unidad fracción restante (fr)**](https://lenguajecss.com/css/grid/que-es-grid/#unidad-fracci%C3%B3n-restante-fr)

En el ejemplo anterior he utilizado **píxels** como unidades de las celdas de la cuadrícula, sin embargo, también podemos utilizar otras unidades (***o incluso combinarlas***): porcentajes, la palabra clave **`auto`** (***que obtiene el tamaño restante***) o la unidad especial de grid **`fr`** (***fracción restante***), que explicaremos a continuación.

Supongamos el siguiente fragmento de código, donde utilizamos las unidades **`fr`**:

es muy fácil predecir el espacio que va a ocupar la cuadrícula, ya que sólo tenemos que sumar todas las unidades para saber el tamaño total, y comparar con cada columna o fila para saber como de grande o pequeña es respecto al total. Así tendremos un mejor control del espacio restante de la cuadrícula, y resultará más intuitivo calcularlo.

> Se pueden combinar varias **unidades diferentes**, como por ejemplo píxeles (**`*px*`**), fracciones restantes (**`*fr*`**), porcentajes (**`*%*`**) y otras combinaciones similares.
> 

### [**Filas y columnas repetitivas**](https://lenguajecss.com/css/grid/que-es-grid/#filas-y-columnas-repetitivas)

En algunos casos, en las propiedades **`grid-template-columns`** y **`grid-template-rows`** podemos necesitar indicar las mismas cantidades un número alto de veces, resultando repetitivo y molesto escribirlas varias veces. Se puede utilizar la función **`repeat()`** para indicar repetición de valores, señalando el número de veces que se repiten y el tamaño en cuestión.

La expresión a utilizar sería la siguiente: **`repeat(número de veces,`** **`tamaño)`**:

```css
 grid-template-columns: 100px repeat(4, 50px) 200px;
  grid-template-rows: repeat(2, 1fr 2fr);
```

Asumiendo que tuvieramos un contenedor grid con 24 ítems hijos en el HTML, el ejemplo anterior crearía una cuadrícula con **6 columnas** y **4 filas**. Recuerda que en el caso de tener más ítems hijos, el patrón se seguiría repitiendo.

### [**Función `minmax()`**](https://lenguajecss.com/css/grid/que-es-grid/#funci%C3%B3n-minmax)

La función **`minmax()`** se puede utilizar como valor para definir rangos flexibles de celda. Funciona de la siguiente forma:

| **Función** | **Descripción** |
| --- | --- |
| **`minmax(min, max)`** | Define un rango entre **`min`** y **`max`**. |

Si establecemos un rango, por ejemplo, **`grid-template-column: minmax(200px, 500px)`**, estaremos indicando que la celda de columna indicada, tendrá un tamaño de **`500px`**, salvo que redimensionemos la ventana del navegador y la hagamos más pequeña, en cuyo caso, el tamaño de la celda podría ir disminuyendo hasta **`200px`**, medida en la cuál se quedaría como mínimo.

```css
  grid-template-columns: repeat(2, minmax(400px, 600px));
  grid-template-rows: repeat(2, 1fr);
```

### [**Los valores `auto-fill` y `auto-fit`**](https://lenguajecss.com/css/grid/que-es-grid/#los-valores-auto-fill-y-auto-fit)

En la función **`repeat()`** es posible utilizar las palabras claves **`auto-fill`** o **`auto-fit`** para indicar al navegador que queremos que **rellene** o **ajuste** el contenedor grid con múltiples elementos hijos dependiendo del tamaño del **viewport** (***región visible del navegador***).

Es decir, si utilizamos **`repeat(auto-fill, minmax(300px, 1fr)`**, el navegador se va a encargar de que los elementos hijos con el tamaño mínimo quepan en la primera fila, y los que no quepan, se desplacen a las siguientes filas del grid, de modo que se aproveche lo mejor posible el contenedor, y consigamos un efecto similar al que se consigue con **media queries**, pero de una forma más directa y con menos código.

```css
display: grid;
grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
```

Si cambiamos el ejemplo anterior a **`auto-fit`** no veremos ninguna diferencia. Sin embargo, si por ejemplo cambiamos el valor mínimo de **`300px`** a **`50px`** (***de modo que no llegue a cubrir la primera fila completamente***), comprobaremos que mientras **`auto-fill`** va **rellenando** la fila del grid y deja el resto del espacio libre, **`auto-fit`** **ajusta** el tamaño de los ítems para que cubran el tamaño máximo de la fila.

### [**Atajo: La propiedad `grid-template`**](https://lenguajecss.com/css/grid/que-es-grid/#atajo-la-propiedad-grid-template)

Si acostumbras a utilizar estas propiedades frecuentemente, puedes utilizar la propiedad **`grid-template`**, que sirve de atajo para muchas cosas, y una de ellas, resumir en una sola propiedad los valores que tenemos en **`grid-template-columns`** y en **`grid-template-rows`**:

| **Propiedad** | **Valores** | **Descripción** |
| --- | --- | --- |
| **`grid-template`** | **none** | *grid-template-rows* / *grid-template-columns* | Atajo para definir dimensiones del grid. |

Esta propiedad convierte en un proceso bastante cómodo el crear grids de unas dimensiones concretas de forma resumida. En el caso de utilizar el valor **`none`**, las propiedades **`grid-template-rows`**, **`grid-template-columns`** y la propiedad **`grid-template-areas`**, que veremos más adelante en el tema de [Grid por áreas](https://lenguajecss.com/css/maquetacion-y-colocacion/grid-css-areas/), se establecen a sus valores por defecto, desactivando su funcionamiento.

En el caso de utilizar unos valores definidos, la propiedad **`grid-template-areas`** se establecerá a **`none`**.

# [**Huecos en grid**](https://lenguajecss.com/css/grid/que-es-grid/#huecos-en-grid)

Por defecto, la cuadrícula tiene todas sus celdas pegadas a sus celdas contiguas. Aunque sería posible darle un **`margin`** a las celdas dentro del contenedor, existe una forma más apropiada: los huecos (***gutters***).

Para especificar los **huecos** (***espacio entre celdas***) podemos utilizar las propiedades **`column-gap`** y/o **`row-gap`**. En ellas indicaremos el tamaño de dichos huecos:

| **Propiedad** | **Descripción** |
| --- | --- |
| **`column-gap`** | Establece el  de los huecos entre columnas (*líneas verticales*). |
| **`row-gap`** | Establece el  de los huecos entre filas (*líneas horizontales*). |

```css
.grid {
column-gap: 100px;
row-gap: 10px;
}
```

Con la primera propiedad **`column-gap`**, establecemos un hueco de **`100px`** entre celda y celda que se encuentre en columna, mientras que con la propiedad **`row-gap`** establecemos un hueco de **`10px`** entre celda y celda que se encuentre en fila. 

### [**Atajo: Grid con huecos**](https://lenguajecss.com/css/grid/que-es-grid/#atajo-grid-con-huecos)

De la misma forma que habrás visto en **flex**, existe una propiedad de atajo para las propiedades **`column-gap`** y **`row-gap`**, que nos permite la posibilidad de no tener que indicar las propiedades por separado. La propiedad en cuestión sería **`gap`** y se utilizaría de la siguiente forma:

```css
.grid {
  /* gap: <row-gap> <column-gap> */
  gap: 20px 80px;
  /* Equivalente a... */
  row-gap: 20px;
  column-gap: 80px;

  gap: 40px;
  /* Equivalente a... */
  row-gap: 40px;
  column-gap: 40px;
}
```

# [**Orden de los elementos**](https://lenguajecss.com/css/grid/alinear-centrar-css/#orden-de-los-elementos)

Por último, tenemos la propiedad **`order`**. Funciona exactamente igual que como funciona en **flex**. Es una propiedad mediante la cual podemos modificar y establecer un orden de los elementos mediante números que actuarán como «peso» del elemento:

| **Propiedad** | **Valor** | **Descripción** |
| --- | --- | --- |
| **`order`** | **0** | | Número (peso) que indica el orden de aparición de los ítems. |

Por defecto, todos los elementos hijos de un contenedor flex tienen establecido un **`order`** por defecto al valor **`0`**. Si indicamos una propiedad **`order`** con un valor numérico diferente, recolocará los ítems según dicho número, colocando antes los elementos con un número **`order`** más pequeño (***incluso números negativos***) y los elementos con números más altos después.

# [**Grid por áreas**](https://lenguajecss.com/css/grid/grid-template-areas/)

Hasta ahora hemos visto como definir cuadrículas **Grid CSS** donde definimos sus filas y sus columnas a través de propiedades como **`grid-template-rows`** y **`grid-template-columns`**. Sin embargo, no es la única forma de definir cuadrículas en CSS. Si necesitamos un poco más de flexibilidad a la hora de definir un grid, podemos utilizar una funcionalidad denominada **Grid por áreas**, que permite de forma casi gráfica y visual, definir mediante texto la ubicación y forma que van a tener las celdas de nuestra cuadrícula.

> **Recuerda**: Los **grids por áreas** no son una alternativa a los **grids explícitos** (***definidos por filas y columnas***). Ambos pueden trabajar conjuntamente o por separado, según interese.
> 

# [**Grid por áreas**](https://lenguajecss.com/css/grid/grid-template-areas/#grid-por-%C3%A1reas)

Mediante los **Grids por área** es posible indicar el nombre y posición concreta de cada área de una cuadrícula. Para ello utilizaremos la propiedad **`grid-template-areas`** en nuestro contenedor padre, donde debemos especificar el orden de las áreas en la cuadrícula. Posteriormente, en cada ítem hijo, utilizamos la propiedad **`grid-area`** para indicar el nombre del área del que se trata y que el navegador pueda identificarlas:

| **Propiedad** | **Descripción** |
| --- | --- |
| **`grid-template-areas`** | Indica la disposición de las áreas en el grid. Cada texto entre comillas simboliza una fila. |
| **`grid-area`** | Indica el nombre del área. Se usa sobre ítems hijos del grid. |

De esta forma, es muy sencillo crear una cuadrícula altamente personalizada en apenas unas cuantas líneas de CSS, con mucha flexibilidad en la disposición y posición de cada área. Veamos un ejemplo:

```css
  display: grid;
  grid-template-areas: "head head"
                       "menu main"
                       "foot foot";
                       
  .item-1 { grid-area: head; background: blue; }
  .item-2 { grid-area: menu; background: red; }
  .item-3 { grid-area: main; background: green; }
  .item-4 { grid-area: foot; background: orange; }
```

> Recuerda que **área** y **nombre de clase** son cosas independientes y diferentes. Es muy importante no confundirlas.
> 

Aplicando este código, conseguiríamos una cuadrícula donde:

- **Item 1** es la cabecera (***head***), que ocupará la primera fila (***toda la parte superior***).
- **Item 2** es el menú lateral (***menu***), que ocupará el área izquierda del grid (***debajo de la cabecera***).
- **Item 3** es el contenido (***main***), que ocupará el área derecha del grid (***debajo de la cabecera***).
- **Item 4** es el pie de cuadrícula (***foot***), que ocupará la última fila (***área inferior del grid***).

![image.png](attachment:d55c8104-dd1a-4349-80cf-c2c5d56583da:image.png)

> OJO: Ten en cuenta añadir contenido de texto en cada celda del grid, ya que si no existe contenido y no has definido un tamaño de fila/columna, el grid se adaptará a su contenido (que no lo hay) y parecerá que no existe. También ten en cuenta que puedes combinar con propiedades como grid-template-columns y/o grid-template-rows para añadirle tamaño o dimensiones.
> 

### [**La propiedad `grid-template-areas`**](https://lenguajecss.com/css/grid/grid-template-areas/#la-propiedad-grid-template-areas)

La propiedad **`grid-template-areas`** es la propiedad principal de este sistema, y debe utilizarse en el contenedor padre **grid**.

| **Propiedad** | **Valores** | **Descripción** |
| --- | --- | --- |
| **`grid-template-areas`** | **none** |  *fila1*,  *fila2*, ... | Define cada fila del grid, indicando el nombre del área a colocar. |

Cada una de estas **filas** se definen como un  donde indicaremos el nombre de un **área** que posteriormente definiremos en nuestro código CSS. Cada fila puede tener ninguna o varias áreas que habría que separar por espacio. A continuación veremos algunos ejemplos de los valores que podemos indicar en esta propiedad y su significado:

| **Valores** | **Descripción** |
| --- | --- |
| **none** | Indica que no se creará ninguna plantilla de áreas. |
| **`"head"`** | Indica que se creará una fila de una columna con el área head. |
| **`"head menu"`** | Indica que se creará una fila de 2 columnas con el área head en una y el área menu en otra. |
| **`"head head"`** | Indica que se creará una fila de 2 columnas con el área head ocupando ambas. |
| **`"."`** | Indica que se colocará una celda sin nombre (*nula*) en esta posición. |

> Recuerda que las áreas deben existir y estar definidas con la propiedad grid-area, de lo contrario, se anulará la propiedad.
> 

### [**La propiedad `grid-area`**](https://lenguajecss.com/css/grid/grid-template-areas/#la-propiedad-grid-area)

Por otro lado, al utilizar la propiedad **`grid-template-areas`** y nombrar varias áreas en su valores, es necesario que dichas áreas estén definidas mediante la propiedad **`grid-area`** en sus elementos hijos. Recuerda no confundir nombre de área, con nombre de clase, puesto que no es lo mismo.

| **Propiedad** | **Valores** | **Descripción** |
| --- | --- | --- |
| **`grid-area`** | **auto** | *nombre* | Da un nombre de área al elemento indicado. |

Esta propiedad permite nombrar un elemento del HTML con un **nombre de área**. Mucho cuidado, ya que este nombre no es un string, y por lo tanto no debe definirse entre comillas **`"`**. Estos nombres se utilizarán en la propiedad **`grid-template-areas`** para definir donde irán ubicados.

Los valores que puede tomar la propiedad **`grid-area`** son los siguientes:

| **Valores** | **Descripción** |
| --- | --- |
| **auto** | Coloca la celda en la próxima área vacía que se encuentre disponible. |
| *nombre* | Le da un nombre de área al elemento en cuestión. |
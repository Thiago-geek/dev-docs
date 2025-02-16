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
# Paso 6: Variables a la escucha

## 1. Reto

Vas a odiarme mucho después de lo sufrido en el paso anterior cuando veas este cambio en el código:

```js
<template>
  ...
  <input type="color" v-model="borderColor" />
  ...
</template>
```

¡Y te olvidas del método y de la atadura (binding) del atributo! (también puedes eliminar el método `changeBorderColor`)

En Vue vieron que esto pasaría, y había que ahorrar trabajo. Lo hicieron con el “two-way binding” que ofrece `v-model` ([documentación](https://vuejs.org/api/built-in-directives.html#v-model)).

¿Me estás mirando mal? Venga que te cuento algo muy jugosito…

### Variables computadas

Hemos visto la forma de crear variables con `data()` pero en Vue hay un método más sofisticado para cuando unas variables dependan de otras.

Estamos haciendo esto para el estilo de la imagen:

```js
  <img :src="imgSrc" :style="`border: 20px solid ${borderColor}`" />
```

 Quedaría más elegante hacer algo así:

```js
  <img :src="imgSrc" :style="imgStyle" />
```

Porque ahora mismo solo queremos cambiar el color del borde, pero, ¿y si queremos cambiar otros atributos del estilo?

Nos vamos a `script` y añades este bloque nuevo justo antes de la última `}` (al mismo nivel que `methods`, no te olvides de la coma)

```js
  computed: {
    imgStyle() {
      return `border: 20px solid ${this.borderColor}`
    }
  }
```
 
¡Ojo al `this`! Claro, hace falta para llamar a la propiedad `borderColor` dentro del JavaScript que entiende Vue.

Las variables computadas escuchan los cambios de otras variables (propiedades) y, cuando estas cambian, también cambian ellas.

Así que `imgStyle` solo cambia cuando lo hace `borderColor`.

### Binding de objetos con class y style

Esto tiene un nombre muy complejo pero no es para tanto.

Tanto para el atributo `class` o el `style` (con el que trabajaremos ahora) Vue permite que juegues con objetos. 

Así podríamos tener convertir esto:

`style="color: white; background: red;" `

En esto otro gracias a un objeto (ojo a las comillas dobles y sumples):

`:style="{ color: 'white', background: 'red' }"`

Más ordenado, mejor pinta y más _accionable_ desde el código.


### 💦 Para que lo resuelvas tú

Trata de crear una variable computada  `imgStyle` que devuelva en vez de una cadena con el estilo un objeto.

En la primera iteración es fácil, pero, ¿y si queremos las propiedades del borde por separado?

Esto `border: 20px solid #FF0000` es un _sugar syntax_ de `border-width: 20px; border-style: solid; border-color: #FF0000;`

> Para nota: Amplia tu variable (propiedad) computada para que devuelva el objeto con la definición de estilo sin acortar.
> Para más nota: ¿Tendría sentido que el `src` de la imagen de nuestra webapp fuera una variable computada? ¿Te atreverías a plantearlo?


## 2. Pistas para encontrar la solución

- [Computed Properties](https://vuejs.org/guide/essentials/computed.html)
- [Binding Inline Styles](https://vuejs.org/guide/essentials/class-and-style.html#binding-inline-styles)

## 3. Resolución

Puedes verla en la rama `step-06` del repositorio de trabajo.

¡Estás on-fire! 🔥 🔥 🔥

Vamos a por el siguiente paso \>\> Cambia a la rama `step-07`
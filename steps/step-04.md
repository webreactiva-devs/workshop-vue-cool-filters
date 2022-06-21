# Paso 4: Un botón que haga algo

## 1. Reto

Dejaste hace dos pasos un _flag_ que hacía que se mostrara la imagen o no en la web.

Sería mucho mejor hacerlo dinámico, ¿verdad?

En la parte de `template` añade un botón:

```js
<template>
  <button @click="showImg = !showImg">Interruptor</button>
  // El código que teníamos antes
</template>
```

Al hacer click en el “interruptor” verás como la primera imagen aparece y desaparece porque cambiamos el valor de `showImg`.

Acabas de manejar tu primer evento en Vue con la directiva `v-on` que estás viendo acortada (y verás así siempre) con una `@`.

Los eventos son propios del DOM no es algo exclusivo de Vue. Los más usados son click, input, change…

### Creando un método

Vamos a ordenar un poco mejor el código y extraer la funcionalidad que tenemos en el template:

```js
<template>
  <button @click="toggleShowImg">Interruptor</button>
  ...
</template> 

<script>
export default {
  data() {
    ...
  },
  methods: {
    toggleShowImg() {
      return this.showImg = !this.showImg
    }
  }
}
</script>
```

¡Ojo! Aquí pasan varias cosas mágicas:
- En el `@click` no es necesario que coloquemos los `()` al método. Vue va a ir a buscar esa función a su `<script>` y ya sabe que no tiene parámetros.
- En `methods` añadimos el método. En Options API se estructura el código de esta forma para que Vue lo entienda.
- Se usa `this.showImg` y no `showImg`, ¿por qué algo tan raro?
	 

### 💦 Para que lo resuelvas tú

La tarea que te propongo es algo más compleja que en pasos anteriores.

Queremos mostrar una sola imagen pero que cambie de forma aleatoria una vez pulsas un botón. Fíjate que las imágenes están en un array `images` pero realmente no se diferencian más que por un solo parámetro.

El método se llamará `changeImage()`. 

> Para nota: La ruta de una imagen cargada por defecto antes de hacer clic al botón.



## 2. Pistas para encontrar la solución

- En JavaScript para conseguir números aleatorios entre 0 y 1 puedes usar [Math.random()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/random)
- Para conseguir eliminar decimales échale un vistazo a [Math.floor()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)

## 3. Resolución

Puedes verla en la rama `step-04` del repositorio de trabajo.

¡Venga que vas muy bien! 👏 👏

Vamos a por el siguiente paso \>\> Cambia a la rama `step-05`

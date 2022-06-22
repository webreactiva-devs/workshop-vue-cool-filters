# Paso 5: Color Picker Tacatá

## 1. Reto

Vamos a ponerle color a la vida y a quitar algunos elementos que ya no nos hacen falta en el `template` y en `script`.

```js
<template>
  <button @click="changeImage">Cambiar imagen</button>
  <hr />
  <img :src="imgSrc" style="border: 20px solid #FF0000" />
</template>

<script>
export default {
  data() {
    return {
      borderColor: "#FF0000",
      imgSrc: "https://source.unsplash.com/200x200/?cocktail,party&v=1",
    };
  },
  methods: {
    changeImage() {
      this.imgSrc = `https://source.unsplash.com/200x200/?cocktail,party&v=${Math.floor(Math.random() * 300)}`;
    }
  }
};
</script>

```

Hemos añadido un borde de color a la imagen y una nueva variable, `borderColor` pero no están conectadas entre sí.


Un recurso muy utilizado en el mundo de JavaScript son las “cadenas de texto de plantilla”. Las hemos usado en el method `changeImage` que tienes justo arriba.

Así que reformulamos el atributo `style` de la imagen.

```js
  <img :src="imgSrc" :style="`border: 20px solid ${borderColor}`" />
```

> [Si quieres saber más de “template strings”.](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Template_literals)
 
Ahora si están conectadas variable y plantilla.

### Selector de color

Saca partido al HTML5 y añadamos un selector de color nativo para modificar el color del borde de la imagen.

```js
<template>
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" @input="changeBorderColor($event)" />
  <hr />
  <img :src="imgSrc" :style="`border: 20px solid ${borderColor}`" />
</template>
```

Ahora te toca a ti.

### 💦 Para que lo resuelvas tú

Haz que el `borderColor` cambie cuando modificas el selector de color.

Primero tienes que crear un método con el nombre que aparece en el evento `input`.

Ese método si va a tener un argumento por defecto: `$event`

¿Dónde está el valor del input cuando cambia? Es una de las preguntas más solicitadas de Javascript y no quiero que se te olvide nunca.

> Para nota: ¿cómo conseguirías que el valor por defecto del selector sea #FF0000 antes de que cambies a otro color? 
> Para nota: ¿podríamos usar la llamada a `changeBorderColor` sin argumentos?


## 2. Pistas para encontrar la solución

- [Event handling en Vue](https://vuejs.org/guide/essentials/event-handling.html#method-handlers)
- Para saber cómo extraer el valor del selector del color cada vez que se lanza el evento `input` usa el ingenio o `console.log($event)` o Stack Overflow.

## 3. Resolución

Puedes verla en la rama `step-05` del repositorio de trabajo.

Vamos a por el siguiente paso \>\> Cambia a la rama `step-06`

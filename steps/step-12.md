# 12. Componentes a cholón (II): del hijo al padre

## 1. Reto

Ahora mismo tu webapp tiene un fantástico slider para definir el valor de la saturación de una imagen molona… ¡pero no funciona!

Nos falta comunicar el componente hijo `SaturateInputFilter.vue` con el padre `App.vue`.

¿Cómo hacerlo?

Tenemos que echar mano de los eventos para aprovecharnos de cuando algo pase en el hijo (el input cambie de valor) el padre se entere (atrape el valor y se lo ponga como estilo a la imagen).

Vamos con un ejemplo:

Coloquemos en `src/components/ButtonPrettyNumber.vue` un `button`:

```js
<template>
	<button @click="$emit('sendPrettyNumber', Math.random()*321)">Consigue un precioso número</button>
</template>
```

Ha aparecido la palabra especial `$emit` que te aseguro no es una variable de PHP. Es un método que nos permite emitir un evento personalizado (custom event) desde el componente hacia otro lugar.

> 👉 Nuestro evento es personalizado, pero tiene que responder a un evento que el navegador sea capaz de capturar, en este caso, el @click 

Ahora en `App.vue` incluimos ese componente hijo:

```js
// src/App.vue

<template>
...
  <ButtonPrettyNumber @sendPrettyNumber="(prettyNumber) => { appPrettyNumber = prettyNumber }" />
  Valor appPrettyNumber: {{appPrettyNumber}}
...
</template>

<script setup>
...
import ButtonPrettyNumber from "./components/ButtonPrettyNumber.vue"

const appPrettyNumber = ref(0);
...
</script>
```

Lo que debería pasar es que cada vez que pulses al botón consigas como resultado un número aleatorio “pintado” en el padre `App.vue`  pero generado en el hijo `ButtonPrettyNumber.vue`

- Fíjate en el nombre del evento personalizado `sendPrettyNumber`. Lo creamos desde el hijo y lo capturamos con un `@` en el padre. 
- La variable reactiva `appPrettyNumber` captura el valor generado por el hijo de forma un poco “marranilla” directamente en el template `(prettyNumber) => { appPrettyNumber = prettyNumber }` podría estar mejor en un método.

Lo sé, tiene lo suyo.

Pero ahora te toca a ti.
 
### 💦 Para que lo resuelvas tú

Está claro que necesitamos que nuestro `SaturateInputFilter` nos envíe los datos cada vez que cambie el input de valor. Ese será nuestro evento de enganche `@input`
 
A partir de ahí tienes que crear un evento personalizado (puedes llamarlo `updateSaturateFilter`. 

Recuerda que el valor del input de tipo _range_ viaja en el evento en `$event.target.value` .

Lo vimos en el `step-05`, por cierto.

A continuación tienes que capturar ese valor en `App.vue` y hacer que el filtro haga su magia en los estilos de la imagen.

Que no se te olvide crear un atributo más en el `state` para que el valor de la saturación sea reactivo ni aplicarlo en los estilos de la imagen con el filter `saturate(value%)`

> Para una nota muy alta: ¿cómo podrías comunicar padre e hijo de tal forma que pudieras dar un valor de inicio a la saturación desde el padre?

> Avanzamos más sobre el tema en la rama `step-12-plus` usando una técnica descrita en la propia documentación de Vue. (Sin cambios en el texto, solo en el código)
 
## 2. Pistas para encontrar la solución

- Sobre todo: [Components Events](https://vuejs.org/guide/components/events.html)
- Para avanzar más sobre el tema: [Events usage with v-model](https://vuejs.org/guide/components/events.html#usage-with-v-model)
- [Saturate filter](https://developer.mozilla.org/es/docs/Web/CSS/filter#saturate())


## 3. Resolución

Puedes verla en la rama `step-11` del repositorio de trabajo.

Lo que queda es pura mandanga, te lo aseguro…

¡Disfruta del éxito copón! 🎁

Vamos a por el siguiente paso \>\> Cambia a la rama `step-12`

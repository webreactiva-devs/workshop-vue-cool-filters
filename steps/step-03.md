# Paso 3: Directivas muy directas

## 1. Reto

La pregunta más famosa en Stack Overflow es la que respondía a la pregunta: “cómo puedo ocultar una capa con jQuery”.

Eres persona moderna y vamos a usar Vue para ello.

Aprovechamos a hacer un pequeño refactor y meter una nueva variable:

```js
<template>
 <img v-if="showImg" :src="imgSrc" />
 <div v-else>No te muestro la imagen y punto</div>
</template>

<script>
export default {
  data() {
    return {
      showImg: true,
      imgSrc: 'https://source.unsplash.com/200x200/?cocktail,party&v=1'
    }
  }
} 
</script>
```

Ese `v-if` que ves ahí es una directiva. Es algo que entiende Vue en el “HTML con esteroides” y lo que hace es añadir un condicional que evalúa una expresión, en este caso una variable a `true`. El `v-else` es lo que se mostrará cuando la condición del `v-if` no se cumpla.

> Juega a cambiar `showImg` a `false` y verás lo que ocurre.



### 💦 Para que lo resuelvas tú

Comprueba como funciona la directiva `v-show` con respecto a `v-if`

> En el punto 2 de más abajo encontrarás la documentación de esta directiva

---- 

### Trabajo con arrays

Algo muy habitual con lo que te enfrentarás en Vue y cualquier otro lenguaje del mundo mundial es con la tarea de usar listas, diccionarios, tuplas (llámalo como te guste) para recorrerlas y hacer algo con ellas.

En la parte del `script` añade esto:

```js
<script>
export default {
  data() {
    return {
      showImg: true,
      imgSrc: 'https://source.unsplash.com/200x200/?cocktail,party&v=1',
      images: [
        "https://source.unsplash.com/200x200/?cocktail,party&v=2",
        "https://source.unsplash.com/200x200/?cocktail,party&v=3",
        "https://source.unsplash.com/200x200/?cocktail,party&v=4",
        "https://source.unsplash.com/200x200/?cocktail,party&v=5",    
      ]
    }
  }
} 
</script>
```


### 💦 Para que lo resuelvas tú

Busca la forma de conseguir que el resultado final sea esto (si, son 4+1, total 5)

```js
<img src="https://source.unsplash.com/200x200/?cocktail,party&v=1">
<img src="https://source.unsplash.com/200x200/?cocktail,party&v=2">
<img src="https://source.unsplash.com/200x200/?cocktail,party&v=3">
<img src="https://source.unsplash.com/200x200/?cocktail,party&v=4">
<img src="https://source.unsplash.com/200x200/?cocktail,party&v=5">
```

Tendrás que utilizar la directiva `v-for`

> Para nota: ¿Por qué tu editor de código te pone en rojo la línea que has cambiado y aún así funciona?
> Para más nota: ¿Podrías usar v-if en combinación con todo lo demás para mostrar todas las imágenes o ninguna?

## 2. Pistas para encontrar la solución

En la primera parte del paso hablamos de la directiva [v-show](https://vuejs.org/api/built-in-directives.html#v-show).

Para la segunda te hará falta consultar esta documentación:

- [v-for](https://vuejs.org/guide/essentials/list.html#v-for) (explicado en la sección de Essentials)
- [v-for](https://vuejs.org/api/built-in-directives.html#v-for) (explicado en la sección de Built-in Directives)


## 3. Resolución

Puedes verla en la rama `step-03` del repositorio de trabajo.


Vamos a por el siguiente paso \>\> Cambia a la rama `step-04`

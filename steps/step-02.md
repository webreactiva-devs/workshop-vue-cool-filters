 Paso 2: Las tres partes

## 1. Reto

Vas a empezar a trabajar directamente sobre un componente de Vue. Los encontrarás con el nombre Single File Components.

Estos componentes tienen tres partes:
- template (obligatoria)
- script
- style

1. Template se ocupa de la parte del HTML (aunque con esteroides)
2. Script es donde alojaremos nuestra lógica de JavaScript
3. Style para las reglas de CSS para el componente o globales

> Si te fijas es como montar una web en pequeñito: HTML, JS y CSS

Visto en el código sería algo así (el orden no es relevante):

<template>
  
</template>

<script>

</script>

<style>

</style>

### Crear tu primer componente

Si te fijas en el código de tu proyecto tienes un fichero `src/App.vue`. 

Elimina todo lo que tiene y cámbialo por esto:

<template>
 <h1>Vue Cool Filters</h1>
 <img src="https://source.unsplash.com/200x200/?cocktail,party&v=1" />
</template>

Verás que no hace falta tener ni `script` ni `style` para que la webapp siga en marcha. 

Aprovecha a borrar el componente `src/components/HelloWorld.vue`

###Añadiendo JavaScript “made in Vue”

**Empezaremos trabajando con la Options API**. 

De esta forma crearemos un modelo de datos que Vue sea capaz de interpretar en nuestro componente.

<template>
 <h1>{{appName}}</h1>
 <img src="https://source.unsplash.com/200x200/?cocktail,party&v=1" />
</template>

<script>
export default {
  data() {
    return {
      appName: 'Vue Cool Filters'
    }
  }
} 
</script>

Fíjate como aquí pasan dos cosas:
- En script creamos una variable dentro de `data()` que Vue va a ser capaz de interpretar
- En template interpolamos la variable con la doble llave `{{appName}}` . Ese es el HTML con “esteroides” del que te hablaba.

----

### Para que lo resuelvas tú

1. Intenta hacer lo mismo para el atributo `scr` de la URL de la imagen. Crea una variable en `data()` que se llame `imgSrc` e intenta que se interpole el valor en la plantilla.

## 2. Pistas para encontrar la solución

- [Attribute Bindings]


## 3. Resolución

Puedes verla en la rama `step-02` del repositorio de trabajo.


Vamos a por el siguiente paso >> Cambia a la rama `step-03`
# Paso 7: La vida del componente

## 1. Reto

El ciclo de vida de un componente en Vue está acompañado de un gráfico muy popular:

![](https://vuejs.org/assets/lifecycle.16e4c08e.png)

A mi este gráfico siempre se me ha hecho excesivo. Está bien, pero cuando ni tan siquiera te haces una idea de “para qué demonios vale un ciclo de vida de un componente” esto te lía más.

Pongámonos en situación.

Imagina que quieres **inicializar** una variable en tu componente porque depende de un factor global y afecta luego a la vida del componente.

Por ejemplo: Cargar una librería, alterar algo en el DOM o leer un parámetro que pasamos por URL.

Imagina que queremos cambiarle el atributo `title`  a la web desde el componente. Es algo chusco, pero va al grano.

Nos vamos a `script` y añades este bloque nuevo justo antes de la última `}`

```js
  mounted() {
    document.title = 'Qué passssa malandriner';
  }
```

_(Fíjate como el título de la página en el navegador -las tabs- ha cambiado)_

En este caso `mounted` es uno de esos momentos en la vida del componente donde podemos acceder a inyectar nuestro código justo antes de que el `App.vue` se “monte” (se empiece a gestionar la reactividad, la plantilla, etc).

Por tanto, `mounted` es un hook que Vue nos deja abierto para poder interactuar con ese momento.

Atento al `()` después del `mounted`. Eso quiere decir que es una función que solo se llama una vez.

### 💦 Para que lo resuelvas tú

Sigamos con `mounted` y busquemos alterar el comportamiento de inicio del color del borde.

Es otro apaño, realmente no lo necesitamos, pero así le damos emoción.

Te doy incluso parte del código:

```js
  mounted() {
    const color = (new URLSearchParams(window.location.search)).get('color')
	// Aquí va tu código
  },
```

Añade un `?color=0000FF` (sin almohadilla) a la URL del navegador e intenta que ese sea el color por defecto del borde de la imagen.

_(No te preocupes ahora por validarlo)_

> Para nota: ¿Pasaría lo mismo con el hook `created()`?

## 2. Pistas para encontrar la solución

- [Component Lifecycle](https://vuejs.org/guide/essentials/lifecycle.html#lifecycle-diagram)
- [URLSearchParams](https://developer.mozilla.org/es/docs/Web/API/URLSearchParams)


## 3. Resolución

Puedes verla en la rama `step-07` del repositorio de trabajo.

¡¡Locurón!!

Vamos a por el siguiente paso \>\> Cambia a la rama `step-08`
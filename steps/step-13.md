# 13. Huecos mágicos con slots


## 1. Reto

Ahora un tema relajadito. El de los `slots` (aunque en Vue 3 incorporaron muchas funcionalidades.

Es la forma que tenemos de pasar determinada información al componente que no necesitamos que sea una variable, puede ser un texto o un HTML.

Ahora tenemos esto:

```js
  <SaturateInputFilter
	...
    label="Saturación"
  ></SaturateInputFilter>
```

¿No te parece más natural esto?
```js
<SaturateInputFilter>
	Saturación
</SaturateInputFilter>
```

¿Cómo lo entiende el hijo?

Bien fácil, haz la prueba.

Coloca `<slot />` en el lugar donde hasta ahora teníamos el `{{label}}`en  `SaturateInputFilter.vue` (dentro de `<template>`)

Allí tendrás ahora tu texto o, incluso, tu HTML completo si escribes `<p>Saturación</p>`, haz la prueba.

> 👉 Esto puede llegar mucho más allá, pero ten en cuenta una cosa: desde el padre no puedes acceder a las propiedades del componente hijo. Recuerda que los componentes encapsulan su información y solo la que nosotros enviamos fuera (con los eventos, por ejemplo) hacen que se puedan compartir. 

### 💦 Para que lo resuelvas tú

Los slots también permiten ponerle un identificador a los huecos y poder tener varios.

Son los llamados _named slots_.

Queremos tener un _slot_ extra en nuestro componente `SaturateInputFilter.vue` que se llame `info` para agregar ayuda contextual tipo “Desliza el punto sobre la guía para cambiar la saturación de la imagen”.


## 2. Pistas para encontrar la solución

- [Slots](https://vuejs.org/guide/components/slots.html)
- [Named Slots](https://vuejs.org/guide/components/slots.html#named-slots)

## 3. Resolución

Puedes verla en la rama `step-13` del repositorio de trabajo.

Vamos a por el siguiente paso \>\> Cambia a la rama `step-14`

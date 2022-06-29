# Paso 10: Cambiando a reactive

## 1. Reto

Hemos usado `ref` en nuestros primeros pasos de la Composition API y la reactividad, pero, no es la única solución.

De hecho la documentación de Vue comienza por `reactive`, la alternativa para manejar objetos (con profundidad) que soporten la reactividad.

Antes de que me preguntes: ¿Cuál es mejor de las dos? Pues depende de hasta dónde quieras llegar. 

Si queremos tener componentes pequeños que controlen el mínimo posible de variables reactivas será cómodo con `ref`. 

Pero si tenemos mucha carga de objetos (por ejemplo a través de llamadas a la API Rest) o apostamos por gestionar estados completos, entonces pasamos a `reactive`. 

Vue quiere dar aquí dos soluciones porque sabe que ambas tienen limitaciones.

Y muy importante:

**Para que Vue pueda hacer su magia necesita controlar las definiciones y las mutaciones sobre las variables, por eso se saca de la manga los ref y reactive.**

---- 

Un ejemplillo para el código:

Si añades esto en la parte del `setup`:

```js
import { reactive } from "vue" 
const state = reactive({ count: 0 })
```

Luego podrás manipular ese contador de esta forma en la parte del template:

```js
<button @click="state.count++">Suma 1 a {{state.count}}</button>
```

Todo funciona, pero, la vida nunca es tan fácil:

### 💦 Para que lo resuelvas tú

Primero de todo eliminamos el `onMouted` que teníamos de las soluciones anteriores y que está estorbando.

Ahora vamos a la chicha. No te va a gustar mucho, pero, como diría Pat Morita, “es por tu bien”.

En nuestro `script` tenemos estas tres variables reactivas:

```js
const borderColor = ref("#FF0000");
const grayscaleFilter = ref(0);
const imgSrc = ref("https://source.unsplash.com/400x400/?cocktail,party&v=1");
```

Cambia eso por algo como esto:

```js
const state = reactive({
	borderColor: "#FF0000",
	grayscaleFilter: 0,
	imgSrc: "https://source.unsplash.com/400x400/?cocktail,party&v=1"
})
```

Ahora te toca cambiar el resto de la lógica del código (tanto en `template` como en `script` para que tu webapp siga funcionando.

¡Adelante!

## 2. Pistas para encontrar la solución

- [Reactivity Fundamentals](https://vuejs.org/guide/essentials/reactivity-fundamentals.html)

> Entender cómo funciona la “gestión del estado” es lo más importante de este taller de iniciación. Repásalo las veces que haga falta porque todo lo demás te resultará más sencillo a partir de aquí.

## 3. Resolución

Puedes verla en la rama `step-10` del repositorio de trabajo.

Vamos a por el siguiente paso \>\> Cambia a la rama `step-11`

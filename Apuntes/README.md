# JavaScript

JavaScript (JS) es un **lenguaje de programación** que se utiliza principalmente para dar interactividad y dinamismo a las páginas web.  
Mientras que **HTML** se encarga de la estructura y **CSS** del diseño visual, **JavaScript** controla el comportamiento y la lógica.

---

## Conceptos iniciales

### Variables

Una **variable** es un espacio donde guardamos información que puede cambiar mientras se ejecuta el programa.
Por ejemplo, podríamos guardar el nombre de un usuario o un número.

Existen tres formas de declarar variables:

```js
var nombre = "Ana";   // Antigua, no recomendada
let edad = 25;        // Moderna, su valor puede cambiar
const PI = 3.1416;    // Constante, no se puede cambiar
```

- `let`: para valores que pueden modificarse.  
- `const`: para valores fijos.  
- `var`: antigua, puede provocar errores de ámbito.

### Sintaxis básica

JavaScript se compone de **instrucciones** que pueden terminar con `;` (aunque no es obligatorio es recomendable ponerlo siempre).  
Los bloques de código se agrupan entre llaves `{}`.

```js
let nombre = "Juan";
if (nombre === "Juan") {
  console.log("Hola, Juan!");
}
```

### Tipos de datos

JavaScript tiene varios tipos de datos básicos:

| Tipo | Ejemplo | Descripción |
|------|----------|-------------|
| String | `"Hola"` | Texto |
| Number | `42`, `3.14` | Números |
| Boolean | `true`, `false` | Verdadero o falso |
| Undefined | `undefined` | Variable sin valor |
| Null | `null` | Valor vacío |
| Object | `{ nombre: "Ana" }` | Colección de datos |
| Array | `[1, 2, 3]` | Lista de valores |

### Tipado dinámico y conversiones

JavaScript **detecta automáticamente** el tipo de dato y puede convertirlos cuando es necesario.

```js
let x = "5";
let y = 2;

console.log(x + y); // "52" (texto)
console.log(Number(x) + y); // 7 (convertido a número)

console.log(typeof x); // string
x = 5
console.log(typeof x); // number

```

---

## Funciones

Una **función** es un conjunto de instrucciones que realiza una tarea.  
Permite reutilizar código.

```js
function saludar() {
  console.log("Hola!");
}

saludar(); // ejecuta la función
```

### Funciones con parámetros

```js
function sumar(a, b) {
  return a + b;
}

let resultado = sumar(3, 4);
console.log(resultado); // 7
```

### Funciones como expresiones

También pueden guardarse en variables:

```js
const restar = function(a, b) {
  return a - b;
};
```

O con **funciones flecha**:

```js
const multiplicar = (a, b) => a * b;
```

### Hoisting

JavaScript **mueve las declaraciones** de funciones y variables al inicio antes de ejecutarlas, por lo que podemos definirlas al final del código aunque se usen al principio.

```js
saludo();

function saludo() {
  console.log("Hola!");
}
```

---

## Ámbitos y condicionales

### Condicional if-else

Permite que el programa decida qué hacer según una condición.

```js
let edad = 18;

if (edad >= 18) {
  console.log("Mayor de edad");
} else {
  console.log("Menor de edad");
}
```

### Operadores de comparación

| Operador | Significado | Ejemplo |
|-----------|-------------|----------|
| `==` | Igual (sin comparar tipo) | `5 == "5"` → true |
| `===` | Igual estricto (compara tipo) | `5 === "5"` → false |
| `!=` | Diferente | `5 != 3` → true |
| `!==` | Diferente estricto | `5 !== "5"` → true |
| `>` `<` `>=` `<=` | Comparaciones numéricas | `edad >= 18` |

### Ámbitos (scope)

El **ámbito** indica **dónde puede usarse una variable** dentro del programa.

```js
let global = "Disponible en todo el programa";

function ejemplo() {
  let local = "Solo dentro de la función";
  console.log(global); // funciona
  console.log(local);  // funciona
}

console.log(global); // funciona
console.log(local);  // error, fuera del ámbito
```

Tipos:

- **Global**: disponible en todo el código.
- **Local**: solo dentro de una función o bloque.

### Comentarios

Los **comentarios** son lineas que no afectan a la logica del programa.

- **En linea**: Se aplican poniendo `//`
- **En bloque**: Se aplican poniendo `/*         */`

```js

let a = "a"; //Definimos la variable (Comentario de una linea)
let b = "b";
console.log(a+b);
/*
Sumamos
la variable
a con la b
*/
```

---

## JavaScript en la Web

JavaScript permite **interactuar con el HTML y el navegador** a través del **DOM** (Document Object Model).

### Formas de incluir JavaScript

- **En línea (no recomendable):**

```html
<button onclick="alert('Hola!')">Haz clic</button>
```

- **Interno:**

```html
<script>
  console.log("Hola desde un script interno");
</script>
```

- **Externo (recomendado):**

```html
<script src="script.js"></script>
```

### El DOM

El **DOM** representa la estructura de una página web como un árbol de elementos que se pueden modificar.

```html
<p id="mensaje">Hola</p>

<script>
  let elemento = document.getElementById("mensaje");
  elemento.textContent = "Hola, mundo!";
</script>
```

Esto cambia el texto del párrafo directamente desde JavaScript.

### Eventos del DOM

Los **eventos** son acciones del usuario (como clics o teclas presionadas).  
Podemos responder a ellos con JavaScript.

```html
<button id="boton">Haz clic</button>

<script>
  const boton = document.getElementById("boton");
  boton.addEventListener("click", () => {
    alert("¡Has hecho clic!");
  });
</script>
```

---

## Conceptos Avanzados

### Tipos de datos Avanzados

- **Array**
  
  Los arrays son tipos de datos que almacenan datos de **cualquier tipo** y se pueden redimensionar. Cada dato posee un indice (posición que ocupan) y la primera posición es la 0.

```js
let array = [] //Array sin datos.
let arrayDatos = ["Dani",23,"JavaScript",true] // Puede contener todo tipo de datos.

console.log(arrrayDatos[0]) // Sacamos por consola el primer elemento -> Dani
```

- **Set**
  
  Los set son una coleccion de elementos únicos, es decir, un array pero no es indexado y no se pueden repetir valores.

```js
let conjunto = new Set(); // Creamos un Set vacío
let conjuntoDatos = new Set(["Dani", 23, "JavaScript", true, "Dani", 23]); // Creamos un Set con algunos datos (incluyendo repetidos)

console.log(conjuntoDatos); // Output: Set(4) { 'Dani', 23, 'JavaScript', true }

conjuntoDatos.add("Dani");// Intentamos añadir un duplicado

console.log(conjuntoDatos.size); // 4 → los duplicados no se agregan
```

- **Map**
  
  Los Map son colecciones de objetos pero en vez de tener un valor, tienen un par clave-valor . Son iterables y mantienen el orden de inserción.

```js
let mapa = new Map();// Creamos un Map vacío

// Añadimos datos
mapa.set("nombre", "Dani");
mapa.set("edad", 23);
mapa.set("lenguaje", "JavaScript");
mapa.set("activo", true);

mapa.set("nombre", "Daniel"); // Si intentamos añadir una clave repetida se sobrescribe el valor anterior

console.log(mapa); // Output: Map(4) { 'nombre' => 'Daniel', 'edad' => 23, 'lenguaje' => 'JavaScript', 'activo' => true }

console.log(mapa.get("nombre")); // Daniel
console.log(mapa.size); // 4 → aunque “nombre” se repitió, no aumenta
```

-**Object**

 Es una estructura que permite almacenar datos mediante pares clave–valor, donde cada clave identifica un valor o propiedad y no son iterables.

```js
let persona = {}; // Creamos un objeto vacío

// Creamos un objeto con datos
let personaDatos = {
  nombre: "Dani",
  edad: 23,
  lenguaje: "JavaScript",
  activo: true
};

console.log(personaDatos.nombre); // Dani

personaDatos.lenguaje = "Java";
personaDatos.pais = "España"; // Añadimos una nueva propiedad

console.log(personaDatos);
/*
{
  nombre: 'Dani',
  edad: 23,
  lenguaje: 'TypeScript',
  activo: true,
  pais: 'España'
}
*/

// Eliminamos una propiedad
delete personaDatos.activo;
console.log(personaDatos);
/*
{
  nombre: 'Dani',
  edad: 23,
  lenguaje: 'TypeScript',
  pais: 'España'
}
*/
```

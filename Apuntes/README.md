# JavaScript

<p align="center">
  <img src="../Images/js.png" width="400" heigth="400" />
</p>

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

### Iteradores

Los iteradores son **métodos** propios de muchos lenguajes de programación que nso permiten crear un bucle en el código.

Los podemos dividir entre **definidos** e **indefinidos**:

- **Definidos**
  
  Sabemos con certeza cuantas veces va a iterar.

  - Bucle **for**:

    El bucle for ejecuta un bloque de código un número determinado de veces usando un contador.

    ```js
    let numero = 1;

    for (let i = 0; i < 4; i++) { 
    // Se define la variable/condicion inicial ( i vale 0 'let i = 0'), mientras que sea (menor que 4 en este caso 'i < 4'), mientras hace (cada iteración vale 1 más 'i++')
      
      console.log(numero);
      numero+=1; // Lo mismo que numero = numero+1;
    }
    // Salida: 1, 2, 3, 4
    ```

    - Bucle **for in**:

      Recorre las propiedades enumerables de un objeto o los índices de un array.

      ```js
      let array = ["A", "B", "C"];

      for (let i in array) { 
        // 'i' es la variable que va tomando **cada índice del array**
        // Primero i = 0, luego i = 1, luego i = 2
        console.log("Índice:", i, "Valor:", array[i]); 
        // Accedemos al valor usando array[i] porque 'i' es solo el índice
      }
      // Salida: 
      // Índice: 0 Valor: A
      // Índice: 1 Valor: B
      // Índice: 2 Valor: C
      ```

    - Bucle **for of**:

      Recorre los valores de objetos **iterables** como arrays, strings o Sets.

      ```js
      let array = ["A", "B", "C"];

      for (let valor of array) { 
        // 'valor' es la variable que va tomando cada elemento del array directamente
        console.log("Valor:", valor);
      }
      // Salida:
      // Valor: A
      // Valor: B
      // Valor: C
      ```

- **Indefinidos**

  No podemos determinar cuantas veces se va a iterar sobre ellos ya que se basan en una condicion.

  -**While**:

    Mientras que se cumpla la condición entra e itera sobre él hasta que no se cumpla.

    ```js
    let number = 0;

    while(number != 6){ // Si number es distinto de 6 entra e itera hasta que sea distinto de 6. SI NUMBER VALE 6 ANTES DE ENTRAR, NO ENTRA AL WHILE.
      number++;
    }
  ```

  -**Do While**:

    El bucle do while hace lo mismo que el while pero minimo entra una vez al código.

    ```js
    let number = 0;

    do{
        number ++; // La parte del do se ejecuta mientras se cumpla la condición del while.
    }while(number != 0 && number < 7); //Aqui vemos la diferencia con el while, ya que la primera vez que entra, number vale 0, pero al ejecutarse una vez sale valiendo 1.
    ```

### Generadores

Los generadores en JavaScript son una forma especial de función que puede pausar su ejecución y reanudarla más tarde, recordando su estado entre llamadas.
Se definen con un asterisco después de function y se retorna un valor con la palabra **yield**.

```js
function* contar() {
  yield 1; //Entrega un valor y pausa la función en ese punto a esperas de llamarse después.
  yield 2;
  yield 3;
}

let generador = contar();

console.log(generador.next()); // Retorna: { value: 1, done: false}
console.log(generador.next()); // Retorna: { value: 2, done: false}
console.log(generador.next()); // Retorna: { value: 3, done: false}
console.log(generador.next()); // Retorna: { value: undefined, done: true} -> Una vez no hay mas valores se retorna valor undefined y  se indica que ya se ha acabado con el done.
```

### Expresiones Regulares

Las expresiones regulares nos sirven para encontrar cadenas de texto en Strings.

```js
let expresionRegular = new RegExp(/[a-z]+/); //En este caso decimos que busque caracteres de la a-z, mínimo 1.

let array = [12, true, "palabra","palabra", 3 , 5.12];

for( let i in array){
  if(i.match(expresionRegular)){ //Si la expresión regular se encuentra en i.
    console.log("Se ha encontrado una cadena en minusculas.");
  }
}
//Hay infinidad de posibilidades para las expresiones regulares, por lo que aquí solo hemos visto que son y su uso.
```

### Excepciones

Las excepciones son eventos que ocurren durante la ejecución del programa y que interrumpen su flujo.
Trataremos estas excepciones usando los métodos **try-catch**.

```js
let dividendo = 8;
let divisor = 0;

try{
  //Aquí va la parte del código que puede soltarnos alguna excepción.
  
  if(divisor === 0){
    throw new Error("División por cero no permitida."); //Lanzamos una excepción personalizada.
  }
  let resultado = dividendo / divisor; //Matematicamente no se puede dividir por cero, aunque en javascript no salte excepción, por eso la lanzamos nosotros.
  console.log("El resultado de la división es: " + resultado);

}catch(error){
  //Aquí va la parte del código a ejecutarse si salta la excepción indicada.
  console.log("Ha ocurrido un error al hacer la division. Error: " + error.message);

} finally { // No es obligatorio poner el finally, solo el try-catch es obligatorio usarlo junto.

  //Aqui va la parte de código que se ejecutará siempre, haya o no excepción.
  console.log("La ejecución del bloque try-catch ha finalizado.");
}
```

## Conceptos Avanzados II y WEB

### Asincronía

#### Template Literals

  ```js
  let nombre = "Dani";
  console.log(`Hola ${nombre}, bienvenido!`); 
  // Permiten incrustar variables y expresiones dentro de strings con `${}`
  // Se usan con comillas invertidas (backticks `)
  ```

#### Promesas

  ```js
  let promesa = new Promise((resolve, reject) => {
    let exito = true;
    exito ? resolve("Todo OK") : reject("Error");
  });
  // Una promesa representa un valor que llegará en el futuro (asincronía)
  // Una promesa puede tomar los valores de Pending, Fullfilled y Rejected.
  promesa.then(console.log).catch(console.error);
  ```

#### Asincronía y async/await

  ```js
  async function obtenerDatos() {
    try {
      let respuesta = await fetch("https://api.example.com");
      let datos = await respuesta.json();
      console.log(datos);
    } catch (error) {
      console.log("Error:", error);
    }
  }
  // async marca la función como asíncrona
  // await pausa la ejecución hasta que se resuelva la promesa
  ```

#### Web API: fetch

  ```js
  fetch("https://api.example.com")
    .then(res => res.json())
    .then(data => console.log(data))
    .catch(err => console.error(err));
  // fetch hace peticiones HTTP (GET, POST, etc.) y devuelve una promesa
  ```

#### Ajax con await

  ```js
  async function cargar() {
    const res = await fetch("datos.json");
    const data = await res.json();
    console.log(data);
  }
  // Uso moderno de AJAX con async/await → más legible
  ```

### Estricto y Componentización

#### Módulos JS

  ```js
  // archivo math.js
  export function sumar(a, b) { return a + b; }

  // archivo app.js
  import { sumar } from './math.js';
  console.log(sumar(2, 3)); // 5
  // Los módulos permiten dividir el código en archivos reutilizables
```

### Entorno Web

#### Local Storage

  Almacena datos en el navegador de forma permanente (persisten al cerrar).

  ```js
  // Guardar datos
  localStorage.setItem("usuario", "Ana");
  localStorage.setItem("edad", "25");

  // Obtener datos
  let nombre = localStorage.getItem("usuario");
  console.log(nombre); // Salida: Ana

  // Eliminar un dato
  localStorage.removeItem("edad");

  // Limpiar todo
  localStorage.clear();
```

#### Session Storage

  Almacena datos solo durante la sesión actual (se borran al cerrar la pestaña).

  ```js
  // Guardar datos
  sessionStorage.setItem("token", "abc123");

  // Obtener datos
  let token = sessionStorage.getItem("token");
  console.log(token); // Salida: abc123

  // Al cerrar la pestaña, los datos desaparecen
```

#### BabelJS

  Convierte código JavaScript moderno a versiones antiguas para compatibilidad.

  ```js
  // Código moderno (ES6+)
  const saludo = (nombre) => `Hola ${nombre}`;

  // Babel lo convierte a:
  var saludo = function(nombre) {
    return "Hola " + nombre;
  };
  ```

#### Webpack

  Empaqueta y optimiza archivos JavaScript, CSS e imágenes en bundles.

  ```js
  // Estructura de proyecto:
  // src/index.js
  // src/utils.js

  // index.js
  import { sumar } from './utils.js';
  console.log(sumar(2, 3));

  // utils.js
  export function sumar(a, b) {
    return a + b;
  }

  // Webpack genera un único archivo bundle.js optimizado
```

### Testing

#### Test Unitarios con MochaJS

  Framework para escribir y ejecutar tests en JavaScript.

  ```js
  // Función a testear
  function sumar(a, b) {
    return a + b;
  }

  // Test con Mocha
  describe('Función sumar', function() {
    it('debe sumar dos números correctamente', function() {
      let resultado = sumar(2, 3);
      if (resultado !== 5) {
        throw new Error('La suma no es correcta');
      }
    });
  });

  // Salida: debe sumar dos números correctamente
```

#### Cypress

  Herramienta para testing de aplicaciones web end-to-end.

  ```js
  // Test de formulario
  describe('Formulario de login', () => {
    it('debe iniciar sesión correctamente', () => {
      // Visitar página
      cy.visit('https://ejemplo.com/login');
      
      // Llenar campos
      cy.get('#usuario').type('ana@email.com');
      cy.get('#password').type('123456');
      
      // Hacer clic en botón
      cy.get('#btnLogin').click();
      
      // Verificar redirección
      cy.url().should('include', '/dashboard');
    });
  });
```

#### Cucumber (BDD)

  Testing basado en comportamiento usando lenguaje natural.

  ```js
  // Archivo .feature
  // Característica: Login
  // Escenario: Usuario inicia sesión exitosamente
  //   Dado que el usuario está en la página de login
  //   Cuando ingresa credenciales válidas
  //   Entonces debe ver el dashboard

  // Implementación en JavaScript
  Given('el usuario está en la página de login', () => {
    cy.visit('/login');
  });

  When('ingresa credenciales válidas', () => {
    cy.get('#usuario').type('ana@email.com');
    cy.get('#password').type('123456');
    cy.get('#btnLogin').click();
  });

  Then('debe ver el dashboard', () => {
    cy.url().should('include', '/dashboard');
  });
  ```

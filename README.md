# Prompts utilizados — PokéDex Explorer

## 1. Desarrollo inicial de la aplicación

Quiero que desarrolles una aplicación web completa llamada **PokéDex Explorer**, un buscador interactivo de Pokémon utilizando exclusivamente **HTML, CSS y JavaScript Vanilla**, sin frameworks.

El proyecto debe estar compuesto únicamente por dos archivos principales:

* `index.html`
* `script.js`

Todo el código JavaScript debe estar contenido en `script.js` y enlazado desde `index.html`. No se debe utilizar JavaScript inline dentro del HTML, excepto para enlazar el archivo externo. El CSS puede estar incluido dentro de `index.html` mediante `<style>`.

La aplicación debe utilizar exclusivamente **PokéAPI REST v2** como fuente principal de información Pokémon, utilizando `fetch()` y programación asíncrona mediante `async/await`. No se deben introducir datos Pokémon manualmente para sustituir información proporcionada por la API.

### Buscador

El usuario debe poder buscar Pokémon mediante:

* Nombre completo.
* Número de Pokédex.
* Coincidencias parciales del nombre, utilizando el catálogo obtenido dinámicamente desde la API.

Debe aceptar búsquedas como:

* `pikachu`
* `25`
* `charizard`
* `150`

La búsqueda debe ser tolerante a mayúsculas y minúsculas y debe poder ejecutarse mediante Enter o mediante un botón.

Si el Pokémon no existe, se debe mostrar un mensaje amigable y no un error técnico de JavaScript.

### Catálogo

La aplicación debe incluir un catálogo visual de Pokémon cargado dinámicamente desde PokéAPI mediante paginación cuando sea necesario.

Cada tarjeta debe mostrar:

* Imagen.
* Número de Pokédex.
* Nombre.
* Tipo o tipos.

Las tarjetas deben permitir seleccionar un Pokémon y visualizar su información completa.

### Filtros

El catálogo debe disponer de filtros por tipo y permitir seleccionar múltiples tipos simultáneamente.

Por ejemplo:

* Fire + Flying
* Water + Ground
* Electric + Flying
* Fire + Dragon

El comportamiento de múltiples filtros debe estar correctamente definido y funcionar mediante intersección de los tipos seleccionados.

Debe existir un botón **“Limpiar filtros”**.

### Información detallada

Al seleccionar un Pokémon se debe mostrar:

* Imagen grande.
* Número de Pokédex.
* Nombre.
* Especie.
* Tipo o tipos.
* Peso.
* Altura.

El peso obtenido desde PokéAPI debe convertirse correctamente de hectogramos a kilogramos.

### Habilidades

Debe existir una sección denominada **“Habilidad destacada”**.

La aplicación debe obtener las habilidades mediante los endpoints oficiales de PokéAPI y determinar cuál puede considerarse la habilidad principal o destacada según los datos disponibles.

No se deben inventar habilidades. Las habilidades ocultas deben identificarse correctamente.

### Evoluciones

Debe mostrarse la familia evolutiva completa utilizando:

* `pokemon-species`
* `evolution-chain`

Debe soportar tanto cadenas lineales como ramas evolutivas múltiples y procesarlas recursivamente.

Cuando la API proporcione condiciones de evolución, mostrar información como:

* Nivel.
* Piedra.
* Intercambio.
* Amistad.
* Otras condiciones disponibles.

No se deben inventar condiciones.

### Primera aparición en el anime

Mostrar una sección llamada **“Primera aparición en el anime”**.

Como PokéAPI no proporciona directamente una base de datos completa de episodios del anime, no se debe inventar esta información.

Si no existe una fuente externa implementada, mostrar:

> “Información del anime no disponible mediante PokéAPI.”

Si se utiliza una fuente externa, debe estar claramente separada de PokéAPI y documentada en `script.js`.

### Imágenes

Utilizar las imágenes proporcionadas por PokéAPI, priorizando las de mayor calidad disponibles.

Si una imagen falla o no existe, utilizar un fallback visual para evitar imágenes rotas.

### Programación asíncrona

Toda comunicación con la API debe utilizar:

* `fetch()`
* `async`
* `await`
* Promesas cuando sea necesario.

Crear funciones separadas para obtener:

* Pokémon.
* Especie.
* Evolución.
* Habilidades.
* Tipos.
* Catálogo.

### Manejo de errores

La aplicación debe controlar correctamente:

* Pokémon inexistente.
* Errores de conexión.
* API temporalmente no disponible.
* Imágenes inexistentes.
* Datos incompletos.
* Búsquedas vacías.

Utilizar `try/catch` y evitar que errores técnicos lleguen directamente al usuario.

### Estados de carga

Mostrar indicadores de carga durante las consultas a la API, por ejemplo:

> “Cargando Pokémon…”

El estado de carga debe desaparecer tanto cuando la petición sea exitosa como cuando falle.

### Diseño

Crear una interfaz moderna inspirada en una Pokédex, con:

* Diseño responsive.
* Buena jerarquía visual.
* Tarjetas.
* Botones modernos.
* Buscador destacado.
* Filtros claros.
* Panel de información detallada.
* Catálogo organizado.

No utilizar React, Vue, Angular, Bootstrap ni Tailwind.

Debe utilizarse únicamente **HTML + CSS + JavaScript Vanilla**.

### Arquitectura

Mantener `script.js` organizado y modular, evitando una única función gigantesca.

Utilizar nombres descriptivos y separar responsabilidades como:

* Obtención de datos.
* Renderizado.
* Filtros.
* Estados de carga.
* Manejo de errores.

### Rendimiento

Evitar cientos o miles de peticiones innecesarias.

Implementar, cuando sea apropiado:

* Caché en memoria.
* `Map` u otra estructura adecuada.
* Prevención de peticiones duplicadas.
* Carga inicial del catálogo.
* `Promise.all()` cuando sea seguro.

### Experiencia de usuario

Cuando se busque un Pokémon:

1. Mostrar loading.
2. Consultar PokéAPI.
3. Obtener información complementaria.
4. Obtener la cadena evolutiva.
5. Procesar los datos.
6. Renderizar la información.
7. Ocultar el loading.
8. Realizar scroll hacia la ficha en dispositivos pequeños cuando sea conveniente.

La aplicación debe sentirse como una aplicación real y no como una demostración básica de `fetch()`.

### Entrega

Entregar únicamente:

* `index.html`
* `script.js`

Ambos deben contener código completo y funcional, listo para copiar y ejecutar.

No utilizar pseudocódigo ni omitir funciones con comentarios como `// aquí iría el código`.

Antes de entregar, verificar todo el flujo de funcionamiento: catálogo, tipos, búsqueda por nombre e ID, filtros simples y múltiples, información detallada, evoluciones, habilidades, manejo de errores, loading y programación con `async/await`.

---

## 2. Corrección de errores y resiliencia ante acciones del usuario

Ahora necesito que tomes MUY en cuenta los **errores de usuario** y revises exhaustivamente la página para detectar bugs.

Por ejemplo, actualmente la Pokébola del título tiene un problema visual: **el círculo central no está correctamente centrado**. Corrige este y cualquier otro problema visual que encuentres.

También quiero mejorar el comportamiento del buscador.

Cuando el usuario escriba parcialmente el nombre de un Pokémon, por ejemplo:

**Buscador: `Pi`**

deben aparecer debajo del buscador opciones relacionadas como:

* Pikachu
* Pidgeot
* Pidgey
* etc.

Las sugerencias deben poder seleccionarse para ejecutar la búsqueda correspondiente.

El sistema debe ser extremadamente resiliente ante errores de usuario. Un usuario podría hacer clic repetidamente, cambiar filtros rápidamente, realizar múltiples búsquedas consecutivas o interactuar con varias opciones al mismo tiempo. **La aplicación no debe crashearse bajo ninguna de estas circunstancias.**

También hay un problema con el índice/catálogo: al buscar números superiores a `10200`, algunas consultas fallan y muestran un error.

La búsqueda debe permitir consultar correctamente Pokémon mediante su **ID**, incluyendo IDs altos cuando sean válidos según PokéAPI.

El ID también debe aparecer dentro de las sugerencias del buscador para que el usuario pueda identificar claramente cada resultado.

La aplicación debe implementar protección contra:

* Clics repetidos.
* Búsquedas simultáneas.
* Respuestas de peticiones antiguas.
* Peticiones duplicadas.
* Errores de red.
* IDs inexistentes.
* Imágenes faltantes.
* Entradas vacías o inválidas.

Una respuesta antigua de la API **nunca debe sobrescribir un resultado más reciente**.

Revisa y corrige todos estos problemas manteniendo la estructura de dos archivos:

* `index.html`
* `script.js`

---

## 3. Interacción con la familia evolutiva

En la familia evolutiva, cada Pokémon debe poder seleccionarse.

Si el usuario hace clic sobre una **pre-evolución o evolución**, debe abrirse su información completa en el mismo panel donde actualmente se muestra el Pokémon seleccionado.

Además, cuando el usuario coloque el mouse sobre una evolución o pre-evolución, pero todavía no haga clic, debe aparecer una vista rápida con:

* ID.
* Tipo o tipos.
* Peso.
* Altura.
* Otros datos básicos relevantes.

El comportamiento esperado es:

* **Hover:** mostrar información resumida.
* **Click:** abrir la ficha completa de ese Pokémon en el panel principal.

También debe ser accesible mediante teclado cuando corresponda.

Mantén la protección existente contra clics repetidos y evita que cargas antiguas sobrescriban información más reciente.

---

## 4. Corrección del fallo del catálogo

Ahora siempre aparece el siguiente error:

> “No se pudo cargar el catálogo. Revisa tu conexión e inténtalo de nuevo.”

Esto ocurre incluso cuando existe una conexión a Internet estable.

Investiga la causa real del problema y corrige la implementación del catálogo.

La aplicación debe ser tolerante a fallos parciales de PokéAPI. Si una tarjeta o petición individual falla, **no debe descartarse todo el catálogo**.

Implementa una estrategia robusta que incluya:

* Carga de Pokémon en lotes.
* Límite de solicitudes concurrentes.
* Reintentos automáticos ante errores transitorios.
* Manejo de rate limiting.
* Manejo de errores de red.
* Renderizado parcial cuando algunas peticiones funcionan y otras fallan.
* Botón **“Reintentar”** cuando ninguna tarjeta pueda cargarse.
* Protección para evitar que una carga anterior sobrescriba una carga más reciente.
* Caché para reducir peticiones innecesarias.

El catálogo debe continuar funcionando aunque PokéAPI tenga fallos parciales.

Mantén el código organizado y valida nuevamente la sintaxis de `script.js`.

Después de realizar las correcciones, verifica que el catálogo, las búsquedas, los filtros y las interacciones sigan funcionando correctamente.


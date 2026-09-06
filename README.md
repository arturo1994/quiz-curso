# Quiz del curso

Un archivo HTML por clase. Cada archivo funciona solo: tiene sus preguntas y todo lo necesario para correr adentro. No hay que instalar nada.

```
index.html      portada con la lista de clases
clase-01.html   quiz de la clase 1
clase-02.html   quiz de la clase 2
clase-03.html   quiz de la clase 3
```

## Publicarlo en internet

1. Entrá a [github.com/new](https://github.com/new) y creá un repositorio **público**. Ponele un nombre, por ejemplo `quiz-curso`.
2. En el repo vacío, hacé clic en **uploading an existing file** y arrastrá los cuatro archivos juntos.
3. Andá a **Settings → Pages**.
4. En *Source* elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y **Save**.
5. Esperá un minuto y recargá. Va a aparecer la dirección:

   `https://TU-USUARIO.github.io/quiz-curso/`

Esa dirección abre la portada. Cada clase también tiene la suya: `.../quiz-curso/clase-02.html`, por si querés guardarte el acceso directo a una en particular.

## Agregar una clase

1. **Duplicá** un archivo de clase y renombralo `clase-04.html`.
2. Abrilo y editá solo el bloque de arriba, el que empieza en `const CLASE = {`. Todo lo que está debajo del comentario "el motor del quiz" queda igual.
3. Cambiá `titulo`, reemplazá las preguntas, y poné `siguiente: "clase-05.html"` (o `null` si es la última).
4. En la clase anterior, actualizá su `siguiente` para que apunte a la nueva.
5. En `index.html`, duplicá un bloque `<li>` y cambiá el archivo, el número y el título.

Así se ve una pregunta:

```js
{
  enunciado: "La pregunta.",
  opciones: [
    "Primera opción",
    "Segunda opción",
    "Tercera opción",
    "Cuarta opción"
  ],
  correcta: 1,
  explicacion: "Por qué la correcta es correcta, y por qué las otras no."
}
```

Tres cosas que conviene tener presentes:

- **`correcta` se cuenta desde 0.** `0` es la primera opción, `1` la segunda, `2` la tercera, `3` la cuarta. Es el error más habitual.
- **Las comas importan.** Va una coma entre pregunta y pregunta, pero no después de la última. Si el quiz aparece en blanco, casi siempre es una coma de más o de menos.
- **Podés poner 2, 3, 4 o 5 opciones.** No hace falta que sean siempre cuatro.

## Probarlo antes de subirlo

Hacé doble clic en `index.html`. Se abre en el navegador y funciona igual que publicado, con los enlaces entre clases incluidos.

## Lo que hace

- Responder pregunta por pregunta, con corrección inmediata y la explicación de por qué.
- Al final, el puntaje y un repaso de lo que fallaste.
- El orden de preguntas y de respuestas cambia en cada intento, para que no memorices posiciones. Para desactivarlo, buscá `const MEZCLAR = true;` dentro del archivo de la clase y cambialo por `false`.
- Se puede responder con las teclas 1 a 4 y avanzar con Enter.
- Al terminar una clase aparece el botón para pasar a la siguiente.

Los resultados no se guardan: al cerrar la pestaña se borran.

## Una diferencia con la versión de un solo archivo

Acá no hay repaso general mezclando todas las clases, porque cada página conoce solo sus propias preguntas. Si ese modo te resulta útil para antes de un examen, se puede recuperar moviendo las preguntas a archivos `.js` aparte.

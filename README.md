# Escuela de Invierno en Bioinformática Avanzada 2027

Sitio web y materiales de la Escuela de Invierno organizada por la Conexión de
Biología Computacional y Bioinformática del CSIC.

Sitio publicado: https://conexionbcb.github.io/Winter_School_2027/

Este repositorio parte de la [Escuela de Verano 2026](https://github.com/ConexionBCB/Summer_School_2026),
con el contenido de aquella edición conservado como punto de partida y marcado
para revisión.

---

## Lo primero: rellenar los datos del curso

Casi todo lo que cambia entre ediciones —fechas, sede, precios, plazos, enlace
al Aula Virtual— está centralizado en el bloque `curso:` de **`_config.yml`**.
Editándolo se actualizan a la vez la portada, el programa y la página de
logística.

Lo que queda pendiente está marcado con `[TBC]`. Para ver todo lo que falta:

```bash
grep -rn "TBC" --exclude-dir=.git .
```

Y los comentarios dirigidos a la organización:

```bash
grep -rn "TODO (organización)" --exclude-dir=.git .
```

## Estructura

| Ruta | Qué es |
|---|---|
| `_config.yml` | **Datos del curso y navegación. Empieza aquí.** |
| `index.md` | Página de inicio |
| `pages/` | Programa, una página por día, Aula Virtual, organización y logística |
| `_data/*.yml` | Listas de profesorado, organizadores y patrocinadores |
| `materials/dayN/` | Material de cada día, con una subcarpeta por ponente |
| `materials/_plantilla-ponente/` | Plantilla de README para cada ponente |
| `_layouts/` | Plantillas Jekyll |
| `assets/css/style.css` | Estilos |
| `docs/moodle/` | Notas sobre el Aula Virtual (no se publican) |
| `CONTRIBUTING.md` | **Guía para el profesorado: cómo subir material** |

## Aula Virtual (Moodle)

El sitio web es estático y no puede alojar Moodle; lo **enlaza**. La página
`/aula-virtual/` y el botón de la portada leen `curso.moodle_url` de
`_config.yml`: mientras esté vacío muestran un aviso de "próximamente", y en
cuanto se rellene aparece el enlace. No hay que editar ninguna página.

La decisión de dónde alojarlo está analizada en
[`docs/moodle/01-opciones-de-alojamiento.md`](docs/moodle/01-opciones-de-alojamiento.md),
y la organización del curso en secciones y roles en
[`docs/moodle/02-estructura-del-aula.md`](docs/moodle/02-estructura-del-aula.md).

## Para el profesorado

Si impartes una sesión, lee [`CONTRIBUTING.md`](CONTRIBUTING.md): explica qué
material va en este repositorio, qué va en el Aula Virtual, y cómo subir cada
cosa (con y sin git).

## Ver el sitio en local

```bash
bundle install
bundle exec jekyll serve
```

Y abrir http://localhost:4000/Winter_School_2027/

## Publicación

GitHub Pages construye el sitio automáticamente al hacer push a `main`. En
**Settings › Pages**, seleccionar *Deploy from a branch* → `main` → `/ (root)`.

Si el repositorio se renombra, hay que actualizar `baseurl` en `_config.yml`
para que coincida con el nombre nuevo, o los enlaces y los estilos se romperán.

## Licencia

<!-- TODO (organización): elegir licencia. Sugerencia: CC BY 4.0 para los
     contenidos y MIT para el código del sitio, igual que es habitual en
     material docente reutilizable. -->
Pendiente de definir.

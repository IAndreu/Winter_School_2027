---
layout: page
title: Aula Virtual
permalink: /aula-virtual/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

El **{{ c.moodle_nombre }}** es la plataforma Moodle donde se distribuye todo el
material del curso y donde se realizan las entregas de las actividades.

{% if c.moodle_url and c.moodle_url != '' %}
<p>
  <a href="{{ c.moodle_url }}" class="btn btn-primary" target="_blank" rel="noopener noreferrer">
    Entrar en el Aula Virtual
  </a>
</p>
{% else %}
<p class="notice notice--pending">
  El Aula Virtual todavía no está abierta. El enlace de acceso se publicará aquí
  y se enviará por correo a las personas inscritas antes del comienzo del curso.
</p>
{% endif %}

## Qué encontrarás

Cada día del curso tiene su propia sección dentro del aula, y dentro de cada
sección hay un bloque por ponente con:

- **Diapositivas y material teórico** (PDF, enlaces).
- **Cuadernos de prácticas** (Jupyter, R Markdown, Quarto) y scripts.
- **Datos de ejemplo** o instrucciones para descargarlos.
- **Foro de dudas** específico de la sesión.
- **Tareas** para las actividades evaluables.

Además hay una sección general con:

- Guía de bienvenida y normas del curso.
- Instrucciones de acceso al servidor de prácticas.
- **Entrega del mini‑syllabus**, necesaria para el reconocimiento de créditos ECTS.
- Encuesta de satisfacción al final de la semana.

## Acceso

- **Participantes:** se crean las cuentas a partir de la lista de personas
  inscritas. Recibirás tus credenciales por correo electrónico antes del inicio
  del curso, junto con las instrucciones de primer acceso.
- **Profesorado:** cada ponente recibe el rol de *Profesor* en su propia sección,
  lo que le permite subir y organizar su material sin depender de la
  organización. Ver la guía de abajo.
- **Problemas de acceso:** escribe a [{{ c.email }}](mailto:{{ c.email }}).

## Guía para el profesorado

Cada ponente gestiona su propio bloque dentro del día que le corresponde. El
procedimiento resumido es:

1. Acepta la invitación que recibirás por correo y entra en el aula.
2. Ve a tu sección (**Día N — tu nombre**) y activa el modo de edición.
3. Añade tus recursos: *Archivo* para diapositivas y datos, *URL* para enlaces
   externos (GitHub, Colab, Zenodo), *Carpeta* para conjuntos de ficheros.
4. Si tu sesión tiene actividad evaluable, añade una *Tarea* con fecha límite.
5. Deja visible al menos el material teórico **una semana antes** de tu sesión.

Los detalles completos (qué formatos usar, límites de tamaño, cómo enlazar
material pesado y qué hacer con datos sensibles) están en la
[guía de contribución del repositorio]({{ site.curso.repo_url }}/blob/main/CONTRIBUTING.md).

## Relación con este repositorio

El material de **acceso abierto** se publica también en este repositorio, en las
carpetas `materials/dayN/`, de modo que siga disponible cuando el aula se cierre
al terminar la edición. El material con restricciones de licencia o los datos de
tamaño grande permanecen únicamente en el Aula Virtual.

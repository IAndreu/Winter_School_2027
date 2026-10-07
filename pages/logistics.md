---
layout: page
title: Logística
permalink: /logistics/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

Información práctica de la {{ site.title }}.

<!-- TODO (organización): los valores marcados como [TBC] se editan en
     `_config.yml`, bloque `curso:`. No hace falta tocar esta página para
     cambiar fechas, precios o sede. -->

## Matrícula

- **Precio:** {{ c.precio }} por persona.
- **Descuento socios SEBiBC:** {{ c.descuento_socios }} de descuento para personas socias de la
  [Sociedad Española de Bioinformática y Biología Computacional (SEBiBC)](https://www.sebibc.es/)
  (precio final {{ c.precio_socios }}).
- La matrícula incluye:
  - Alojamiento en **pensión completa** (desayuno, comida, cena y pausas de café).
  - Acceso a todas las sesiones teóricas y prácticas.
  - Material docente proporcionado durante el curso, disponible en el
    [Aula Virtual]({{ site.baseurl }}/aula-virtual/).
  - Acceso al servidor donde se realizan las sesiones prácticas.

## Fechas y horario

- **{{ c.fechas_largo }}**.
- Sesiones (de martes a jueves): **10:00–13:30** y **14:30–18:00**
  (pausa para comer de 13:30 a 14:30).
  - El lunes las actividades comenzarán después de la comida.
  - El viernes por la tarde no habrá sesiones para facilitar los viajes de vuelta.

> Al celebrarse en invierno, ten en cuenta las horas de luz y las condiciones
> meteorológicas al planificar los desplazamientos. Recomendamos llegar la tarde
> anterior al comienzo del curso.

## Sede

La Escuela de Invierno se celebrará en **{{ c.sede }}**.

- **Dirección:** {{ c.sede_direccion }}
{% if c.sede_web and c.sede_web != '' %}- **Web de la sede:** <{{ c.sede_web }}>
{% endif %}

El alojamiento incluido en la matrícula será en **{{ c.alojamiento }}**
(los detalles concretos se comunicarán a las personas inscritas).

## Cómo llegar

<!-- TODO (organización): sustituir esta sección por las indicaciones concretas
     de la sede (aeropuerto, estación de tren, autobuses urbanos, taxis).
     En la edición de verano 2026 esta sección cubría avión, tren, autobús y
     transporte interno; puede servir como modelo. -->

Las indicaciones detalladas para llegar a **{{ c.ciudad }}** (aeropuerto más
cercano, estación de tren, autobuses y transporte urbano) se publicarán aquí en
cuanto se confirme la sede.

## Requisitos previos

- Familiaridad con la línea de comandos (Unix/Linux) y con conceptos de
  bioinformática (R, Python, análisis de RNA‑Seq, llamado de variantes, etc.).
- El curso está orientado a personas que ya trabajan o estudian en bioinformática
  y quieren profundizar en temas avanzados. Resulta especialmente útil para
  quienes preparan o imparten docencia en estas áreas.
- Será necesario un portátil con conexión a internet y un navegador actualizado
  para acceder al [Aula Virtual]({{ site.baseurl }}/aula-virtual/) y al servidor
  de prácticas.

## Reconocimiento de créditos ECTS

La Escuela de Invierno ofrece la posibilidad de reconocimiento de **créditos
ECTS**. Para ello, las personas participantes deberán:

- Asistir a las sesiones del curso (según los criterios que se especifiquen).
- Elaborar y entregar un **syllabus breve** sobre uno de los temas tratados
  durante la semana, siguiendo la plantilla y criterios explicados el día 1.

La entrega del mini‑syllabus se realiza a través del
[Aula Virtual]({{ site.baseurl }}/aula-virtual/) y podrá hacerse hasta **dos
semanas después** de la finalización del curso.

La información detallada sobre número de créditos y procedimiento administrativo
de reconocimiento se comunicará antes del inicio del curso.

## Contacto

- **Correo de contacto:** [{{ c.email }}](mailto:{{ c.email }})
{% if c.preinscripcion_url and c.preinscripcion_url != '' %}- **Preinscripción:** [Formulario de preinscripción]({{ c.preinscripcion_url }}), abierto hasta el {{ c.preinscripcion_cierre }}.

<p style="margin-top: var(--space-lg);">
  <a href="{{ c.preinscripcion_url }}" class="btn btn-secondary btn-preinscripcion" target="_blank" rel="noopener noreferrer">Preinscripción</a>
</p>
{% else %}
- **Preinscripción:** el formulario se publicará próximamente. Plazo previsto de
  cierre: {{ c.preinscripcion_cierre }}.
{% endif %}

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
     cambiar fechas, precios o plataforma de videoconferencia. -->

## Formato

Esta edición es **{{ c.modalidad }}**. Todas las sesiones, teóricas y prácticas,
se imparten por videoconferencia desde el
[Aula Virtual]({{ site.baseurl }}/aula-virtual/). No hay desplazamiento, ni sede
física, ni alojamiento.

**Plazas limitadas a {{ c.plazas }} participantes.** El curso es una escuela con
sesiones prácticas guiadas, no un seminario abierto: el límite existe para que
el profesorado pueda atender a cada persona durante los ejercicios.

## Matrícula

- **Precio:** {{ c.precio }} por persona.
- **Descuento socios SEBiBC:** {{ c.descuento_socios }} de descuento para personas socias de la
  [Sociedad Española de Bioinformática y Biología Computacional (SEBiBC)](https://www.sebibc.es/)
  (precio final {{ c.precio_socios }}).
- La matrícula incluye:
  - Acceso a todas las sesiones en directo.
  - Acceso al [Aula Virtual]({{ site.baseurl }}/aula-virtual/) con todo el
    material docente.
  - Acceso al servidor donde se realizan las sesiones prácticas, sin necesidad
    de instalar nada en el ordenador propio.
  - Certificado de asistencia.

## Fechas y horario

- **{{ c.fechas_largo }}**.
- Sesiones (de martes a jueves): **10:00–13:30** y **14:30–18:00**
  (pausa para comer de 13:30 a 14:30).
  - El lunes las actividades comenzarán después de la comida.
  - El viernes por la tarde no habrá sesiones.

> **Todos los horarios están en {{ c.zona_horaria }}.** Si participas desde otro
> huso horario, comprueba la diferencia antes del primer día. El calendario del
> Aula Virtual muestra las horas ya convertidas a la zona de tu perfil.

En las sesiones largas habrá pausas cortas cada 60–75 minutos. Seguir un curso
intensivo por videoconferencia cansa más que hacerlo en persona, y el programa
lo tiene en cuenta.

## Requisitos técnicos
{: #requisitos-tecnicos }

Lo que necesitas para seguir el curso:

| | Mínimo | Recomendado |
|---|---|---|
| Conexión | 5 Mbps de bajada / 2 de subida | 20 Mbps, por cable antes que por wifi |
| Navegador | Chrome, Firefox, Edge o Safari actualizados | Chrome o Firefox al día |
| Audio | Auriculares con micrófono | Auriculares con micrófono (evitan el eco) |
| Cámara | Recomendada | Recomendada |
| Pantalla | 1 monitor | **2 monitores o 2 dispositivos**: uno para la clase y otro para practicar |

Dos puntos que marcan la diferencia:

- **Usa auriculares.** El altavoz del portátil provoca eco y obliga a silenciar
  a todo el mundo, lo que mata las preguntas.
- **Dos pantallas, o un segundo dispositivo.** Las sesiones prácticas consisten
  en seguir al ponente mientras escribes tus propios comandos. Con una sola
  pantalla pequeña se vuelve incómodo. Una tablet o un segundo portátil para la
  videollamada sirve perfectamente.

No hace falta instalar software de bioinformática: las prácticas se hacen en un
**servidor remoto** al que se accede con el navegador. Las instrucciones de
acceso estarán en el Aula Virtual antes del comienzo.

**Prueba de conexión:** unos días antes del curso se abrirá una sala de prueba
en el Aula Virtual para que compruebes cámara, micrófono y acceso al servidor.
Dedícale cinco minutos: resolver un problema de audio el lunes a las 10:00
cuesta mucho más.

## Cómo funcionan las sesiones

- **Entrada a las clases:** desde el Aula Virtual, en la sección del día
  correspondiente. No se publican enlaces de videollamada en esta web.
- **Preguntas:** en voz, levantando la mano, o por el chat de la sesión. Cada día
  tiene además un foro para dudas que surjan después.
- **Prácticas:** el profesorado puede abrir salas pequeñas para atender dudas
  concretas sin interrumpir al resto del grupo.
- **Cámara:** se recomienda tenerla encendida al menos en las presentaciones y
  durante las prácticas. Ayuda mucho a que el profesorado sepa si el grupo está
  siguiendo el ritmo.

<!-- TODO (organización): confirmar si se graban las sesiones. Si se graban,
     hace falta recoger consentimiento explícito en la inscripción y decidir
     cuánto tiempo se conservan las grabaciones. Ver
     docs/moodle/03-videoconferencia.md -->

## Requisitos previos

- Familiaridad con la línea de comandos (Unix/Linux) y con conceptos de
  bioinformática (R, Python, análisis de RNA‑Seq, llamado de variantes, etc.).
- El curso está orientado a personas que ya trabajan o estudian en bioinformática
  y quieren profundizar en temas avanzados. Resulta especialmente útil para
  quienes preparan o imparten docencia en estas áreas.

## Reconocimiento de créditos ECTS

La Escuela de Invierno ofrece la posibilidad de reconocimiento de **créditos
ECTS**. Para ello, las personas participantes deberán:

- Asistir a las sesiones del curso. Al ser en línea, la asistencia se registra
  automáticamente a partir de la conexión a cada sesión.
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

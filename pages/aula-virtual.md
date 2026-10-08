---
layout: page
title: Aula Virtual
permalink: /aula-virtual/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

El **{{ c.moodle_nombre }}** es la plataforma Moodle donde ocurre el curso. Al ser
una edición {{ c.modalidad }}, desde el aula se entra a las clases en directo, se
descarga el material, se accede al servidor de prácticas y se entregan las
actividades.

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

## Las clases en directo

Las sesiones se imparten por videoconferencia **desde dentro del aula**: en la
sección de cada día hay un enlace de acceso a la sala de ese día.
{% if c.videoconferencia and c.videoconferencia != '[TBC]' %}
La plataforma utilizada es **{{ c.videoconferencia }}**, integrada en Moodle: se
abre en el navegador, sin instalar nada.
{% endif %}

Los enlaces de las sesiones **no se publican en esta web**, y por una razón
concreta: una sala cuyo enlace circula libremente puede recibir visitas no
deseadas en mitad de una clase. Entrando desde el aula, solo accede quien está
inscrito.

Cómo es una sesión:

- **Entrada:** desde la sección del día, 10 minutos antes de la hora.
- **Preguntas:** en voz, levantando la mano, o por el chat. Cada día tiene además
  un foro de dudas para después de la sesión.
- **Prácticas:** se trabaja en el servidor remoto mientras el ponente guía. El
  profesorado puede abrir salas pequeñas para atender dudas concretas sin parar
  al grupo entero.
- **Pausas:** cada 60–75 minutos en las sesiones largas.

{% if c.grabaciones == 'sí' %}
Las sesiones **se graban** y la grabación queda disponible en la sección del día
para las personas inscritas. Al inscribirte se te pedirá consentimiento
explícito; si prefieres no aparecer, basta con mantener la cámara apagada y usar
el chat en lugar del micrófono.
{% elsif c.grabaciones == 'no' %}
Las sesiones **no se graban**. El material queda disponible en el aula, pero las
clases hay que seguirlas en directo.
{% endif %}

> **Antes del primer día:** entra en la **sala de prueba** que estará abierta en
> la sección general del aula y comprueba cámara, micrófono y acceso al servidor
> de prácticas. Son cinco minutos que evitan empezar el lunes con un problema
> técnico.

## Qué encontrarás

Cada día del curso tiene su propia sección, y dentro de cada sección un bloque
por ponente con:

- **Acceso a la sesión en directo** de ese día.
- **Diapositivas y material teórico** (PDF, enlaces).
- **Cuadernos de prácticas** (Jupyter, R Markdown, Quarto) y scripts.
- **Datos de ejemplo** o instrucciones para acceder a ellos en el servidor.
- **Foro de dudas** específico de la sesión.
- **Tareas** para las actividades evaluables.

Y una sección general con:

- Guía de bienvenida, normas y horarios con zona horaria.
- Sala de prueba técnica.
- Instrucciones de acceso al servidor de prácticas.
- **Entrega del mini‑syllabus**, necesaria para el reconocimiento de créditos ECTS.
- Encuesta de satisfacción al final de la semana.

## Requisitos técnicos

Resumen: navegador actualizado, **auriculares con micrófono** y, si es posible,
**dos pantallas** (una para la clase, otra para practicar). No hace falta
instalar software de bioinformática. Los detalles, con los mínimos de conexión,
están en la página de [Logística]({{ site.baseurl }}/logistics/#requisitos-tecnicos).

## Acceso

- **Participantes:** se crean las cuentas a partir de la lista de personas
  inscritas. Recibirás tus credenciales por correo electrónico antes del inicio
  del curso, junto con las instrucciones de primer acceso.
- **Profesorado:** cada ponente recibe el rol de *Profesor* en su propia sección,
  lo que le permite subir y organizar su material y moderar su sesión sin
  depender de la organización.
- **Problemas de acceso:** escribe a [{{ c.email }}](mailto:{{ c.email }}).
  Durante los días del curso habrá una persona de la organización disponible
  para incidencias técnicas; su contacto se indica en la sección general.

## Guía para el profesorado

Cada ponente gestiona su propio bloque dentro del día que le corresponde:

1. Acepta la invitación que recibirás por correo y entra en el aula.
2. Ve a tu sección (**Día N — tu nombre**) y activa el modo de edición.
3. Añade tus recursos: *Archivo* para diapositivas y datos, *URL* para enlaces
   externos (GitHub, Colab, Zenodo), *Carpeta* para conjuntos de ficheros.
4. Si tu sesión tiene actividad evaluable, añade una *Tarea* con fecha límite.
5. Deja visible al menos el material teórico **una semana antes** de tu sesión,
   para que quien quiera pueda prepararla.
6. **Haz una prueba técnica** con la organización unos días antes: compartir
   pantalla, audio y, si vas a usarlas, salas pequeñas para las prácticas.

El punto 6 es específico de esta edición en línea y conviene no saltárselo:
compartir una terminal legible para 30 personas requiere ajustar el tamaño de
letra, y es mejor descubrirlo antes.

Los detalles completos (qué formatos usar, límites de tamaño, cómo enlazar
material pesado, cómo dar una clase práctica en línea y qué hacer con datos
sensibles) están en la
[guía de contribución del repositorio]({{ site.curso.repo_url }}/blob/main/CONTRIBUTING.md).

## Relación con este repositorio

El material de **acceso abierto** se publica también en este repositorio, en las
carpetas `materials/dayN/`, de modo que siga disponible cuando el aula se cierre
al terminar la edición. El material con restricciones de licencia y los datos de
tamaño grande permanecen únicamente en el Aula Virtual o en el servidor de
prácticas.

# Estructura del Aula Virtual

Cómo se organiza el curso en Moodle para que **cada ponente gestione su propio
material y modere su propia sesión en directo** sin pasar por la organización, y
sin poder romper el trabajo de otra persona.

Esto vale igual para las tres opciones de alojamiento del documento anterior.
Siendo la edición 100 % en línea, cada sección contiene además la clase en
directo de ese día, y el rol de *Profesor* es también lo que da a cada ponente
permiso de **moderador** en su sala.

## La decisión de fondo: un curso, no siete

Hay dos formas de montarlo:

- **Un curso por ponente.** Permisos limpios, pero las participantes acaban con
  siete cursos sueltos, el calendario se fragmenta y las entregas quedan
  repartidas. Para una escuela de una semana es desproporcionado.
- **Un único curso con una sección por sesión.** Una sola lista de inscripción,
  un calendario, un libro de calificaciones. Es lo adecuado aquí.

Se elige la segunda. El matiz —que es lo que hace que funcione— es que en Moodle
el rol de *Profesor* se puede asignar **en el contexto de una sección concreta**,
no solo en el del curso entero. Así cada ponente edita su sección y solo la suya.

## Mapa del curso

```
Escuela de Invierno en Bioinformática Avanzada 2027
│
├── Sección 0 — General (siempre visible arriba)
│     ├── Avisos (foro, solo organización escribe)
│     ├── Guía de bienvenida, normas y horarios CON ZONA HORARIA
│     ├── ▶ SALA DE PRUEBA TÉCNICA (abierta la semana anterior)
│     ├── Requisitos técnicos y guía de la videollamada
│     ├── Programa de la semana (enlace al sitio web)
│     ├── Acceso al servidor de prácticas (credenciales)
│     ├── Contacto de guardia para incidencias técnicas
│     ├── Foro general de dudas
│     └── Lista de participantes / presentaciones
│
├── Sección 1 — Día 1: Bienvenida y docencia
│     ├── Diapositivas: diseño de un syllabus
│     ├── Recursos para la docencia (carpeta)
│     ├── Plantilla de mini-syllabus (archivo)
│     └── Foro de dudas del día 1
│
├── Sección 2 — Día 2: [tema] — [ponente]
├── Sección 3 — Día 3: [tema] — [ponente]
├── Sección 4 — Día 4: [tema] — [ponente]
├── Sección 5 — Día 5: [tema] — [ponente]
│     (cada una con: teoría · práctica · datos · foro propio)
│
└── Sección 6 — Evaluación y cierre
      ├── TAREA: entrega del mini-syllabus (ECTS)
      ├── Criterios de evaluación (rúbrica)
      ├── Encuesta de satisfacción
      └── Certificados
```

Si un día tiene dos ponentes (mañana y tarde), se usan dos secciones
consecutivas en lugar de una, cada una con su responsable. Es preferible a
compartir una sección entre dos personas: mantiene los permisos simples.

## Roles y permisos

| Rol | Quién | Puede |
|---|---|---|
| **Gestor** | Coordinación (2 personas) | Todo: crear secciones, inscribir, configurar, exportar |
| **Profesor** (en su sección) | Cada ponente | Editar **su** sección: subir, ordenar, crear tareas y foros, calificar lo suyo, y **moderar su sala** |
| **Profesor sin permiso de edición** | Ponentes invitados, observadores | Ver todo y participar en foros, sin modificar |
| **Estudiante** | Participantes inscritos | Ver material visible, entregar tareas, escribir en foros, **entrar en las salas como participante** |

Dos personas con rol de Gestor, no una. Si la única persona con permisos no está
disponible el lunes del curso, el problema es serio y perfectamente evitable.

**Y en una edición en línea, una persona de la coordinación con rol de moderador
en todas las salas.** No para dar clase, sino para abrir la sala si el ponente
llega tarde, admitir a quien se quede fuera, silenciar un micrófono abierto y
atender el chat mientras el ponente explica. Es un papel real: conviene
asignarlo por días y que esté escrito quién lo cubre cada mañana.

### Asignar un ponente a su sección

En Moodle 4.x/5.x, con el modo de edición activado:

1. En la sección correspondiente, menú **⋮ › Asignar roles locales**
   (si no aparece, está en **Participantes › Inscripciones**: primero se inscribe
   a la persona en el curso, después se le da el rol local en la sección).
2. Inscribir a la persona en el curso como *Profesor sin permiso de edición*.
3. En el contexto de **su** sección, asignarle *Profesor*.

Resultado: ve todo el curso, edita solo lo suyo.

> Si el Moodle institucional no permite roles locales por sección (algunas
> configuraciones los restringen), la alternativa es dar *Profesor* en todo el
> curso y acordar por escrito que nadie toca la sección de otra persona. Funciona
> en un grupo pequeño que se conoce, pero conviene hacer copia de seguridad del
> curso antes de abrir la edición al profesorado.

## Convenciones dentro de cada sección

Para que las ocho secciones no parezcan ocho cursos distintos, se fija un patrón
y se deja ya creado en las secciones vacías, como ejemplo a rellenar:

```
Día N — [Tema] — [Ponente]
  Descripción: 2–3 frases + objetivos de aprendizaje
  ├── 00 · ▶ SESIÓN EN DIRECTO — 10:00 (actividad de videoconferencia)
  ├── 01 · Teoría — [tema] (archivo PDF)
  ├── 02 · Guion de prácticas (archivo o página)
  ├── 03 · Datos y entorno (URL al servidor, con checksum)
  ├── 04 · Material complementario (carpeta, opcional)
  ├── 05 · Grabación de la sesión (enlace, si se graba)
  └── Foro de dudas — Día N
```

El elemento `00` es la propia actividad de videoconferencia, y va **siempre
primero y bien visible**: es lo que la gente busca a las 09:58 de la mañana.
Conviene que el nombre incluya la hora y, si el grupo es internacional, la zona
horaria.

El prefijo numérico es lo único realmente importante: Moodle ordena por posición
manual y, sin números, al cabo de tres subidas nadie sabe por dónde empezar.

## Visibilidad progresiva

Las secciones de los días se mantienen **ocultas** hasta una semana antes de cada
sesión, y se van abriendo. Razones: evita que alguien estudie una versión del
material que el ponente aún va a cambiar, y mantiene la portada del curso
manejable. Se puede automatizar con **restricciones de acceso por fecha**, de
modo que no haya que acordarse de abrirlas a mano.

La sección 0 y la de evaluación están visibles desde el primer día.

**Excepción en una edición en línea:** la sala de prueba técnica de la sección 0
tiene que estar abierta **la semana anterior**, no el primer día. Es el único
elemento del aula que se usa antes de que empiece el curso, y es el que evita la
media hora de caos del lunes por la mañana.

## Inscripción de participantes

Para ~40 personas, la vía más simple es **subida por fichero CSV**
(*Administración del sitio › Usuarios › Subir usuarios*), generado a partir de la
hoja de inscripciones:

```csv
username,password,firstname,lastname,email,course1,role1
agarcia,changeme,Ana,García,ana@ejemplo.org,invierno2027,student
```

Moodle fuerza el cambio de contraseña en el primer acceso. Alternativa:
**auto-inscripción con clave**, enviando la clave solo a quien haya pagado la
matrícula. Es menos trabajo, pero deja la puerta abierta si la clave circula.

Recomendación: CSV para participantes, alta manual para el profesorado.

## Protección de datos

Puntos a resolver antes de abrir el aula, sea cual sea el alojamiento:

- **Base jurídica** para tratar los datos de participantes (la ejecución de la
  matrícula) y aviso de privacidad visible en el primer acceso.
- **Minimizar**: no pedir más datos de los necesarios. DNI, teléfono o afiliación
  detallada rara vez hacen falta en el aula.
- **Plazo de conservación** definido y escrito: p. ej. borrado de cuentas seis
  meses después del curso, conservando solo las calificaciones necesarias para
  el certificado ECTS.
- **Grabaciones de sesiones**, si las hay: requieren consentimiento explícito y
  separado, recogido en el formulario de inscripción y no al entrar en la sala.
  En un curso en línea esto deja de ser hipotético: hay que decidirlo (ver
  [03-videoconferencia.md](03-videoconferencia.md)) y también preguntar al
  profesorado, que puede no querer ser grabado.
- **Registros de conexión** a las videollamadas: son datos de asistencia y, si se
  usan para los ECTS, hay que decirlo. Conservar solo lo necesario para emitir el
  certificado.
- Moodle incluye herramientas de RGPD (*Política del sitio*, *Solicitudes de
  datos*): conviene activarlas en lugar de improvisar.

## Al terminar la edición

1. **Copia de seguridad completa** del curso (`.mbz`), con datos de usuario, y
   guardarla fuera de la plataforma.
2. **Copia sin datos de usuario**: es la que sirve de plantilla para la edición
   siguiente, y la que se puede compartir.
3. **Volcar el material abierto** a `materials/dayN/` en este repositorio, que es
   lo que sobrevive al cierre del aula.
4. **Descargar las entregas** necesarias para los certificados ECTS.
5. **Cerrar el curso** a nuevas inscripciones y, pasado el plazo de conservación,
   borrar las cuentas.

El paso 3 es el que se olvida, y es el que determina si el trabajo de siete
ponentes sigue existiendo dentro de dos años o desaparece con la suscripción.

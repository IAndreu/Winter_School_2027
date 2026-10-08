# Videoconferencia para el curso en línea

Documento de decisión. Octubre de 2026.

Al ser la edición 100 % en línea, la videoconferencia **no es un extra del
Moodle: es el aula**. Si falla a las 10:00 del lunes, no hay plan B presencial.
Eso cambia los criterios: la fiabilidad y el soporte pesan más que el precio.

## Qué tiene que soportar

| Requisito | Valor |
|---|---|
| Participantes simultáneos | **~40** (30 estudiantes + 7–8 ponentes y coordinación) |
| Duración de sesión | **3,5 h seguidas**, dos veces al día |
| Total | 5 días, ~30 h de directo |
| Compartir pantalla | Imprescindible, con **terminal legible** |
| Salas pequeñas | Muy recomendable, para atender dudas en las prácticas |
| Grabación | Deseable (ver más abajo) |
| Integración en Moodle | Necesaria: asistencia automática y acceso controlado |

Dos cifras concretas descartan opciones antes de empezar: **40 participantes** y
**sesiones de 3,5 horas**. Casi todos los planes gratuitos se quedan por debajo
de una de las dos.

---

## Opción 1 — BigBlueButton integrado en Moodle

BigBlueButton (BBB) es el sistema de videoconferencia pensado para docencia que
Moodle trae **como actividad estándar**; desde Moodle 5.3 viene activada por
defecto en instalaciones nuevas. Está diseñado para clases, no para reuniones:
pizarra, encuestas, mano alzada, notas compartidas, salas pequeñas y vista de
presentación.

**La trampa del servidor gratuito.** Moodle ofrece un servidor BBB de prueba, y
sus límites lo hacen inservible aquí:

- **25 usuarios simultáneos** — por debajo de nuestros 40.
- **60 minutos por sesión** — frente a sesiones de 3,5 h.
- Grabaciones que **caducan a los 7 días** y no se pueden descargar.
- Webcams de estudiantes visibles solo para el moderador.

Además, **desde Moodle 5.3 ya no se incluyen credenciales de API por defecto**:
hay que introducir servidor y secreto propios. Es decir: BBB en core no significa
BBB funcionando; hace falta un servidor BBB detrás.

Ese servidor puede venir de tres sitios: incluido en MoodleCloud (opción 2),
alojado por un proveedor especializado, o montado por nosotros (opción 4).

**A favor**

- Pensado para dar clase: la vista de presentación y la pizarra se notan.
- Integración nativa: asistencia, calendario y acceso controlado sin plugins.
- Sin límite de licencias por ponente.
- Software libre: ninguna dependencia de contrato.

**En contra**

- El servidor gratuito no sirve para este curso.
- Con 40 personas y vídeo, consume bastante CPU y ancho de banda: no es
  indiferente dónde esté alojado.
- Menos familiar para el profesorado que Zoom o Teams, lo que obliga a la prueba
  previa.

---

## Opción 2 — MoodleCloud con BBB incluido  ⭐ recomendada

MoodleCloud incluye videoconferencia BBB integrada **para hasta 100 usuarios**,
sin montar ni mantener servidor alguno. Con 40 participantes vamos sobrados.

**Planes y almacenamiento** (facturación anual, USD, octubre de 2026):

| Plan | Precio/año | Usuarios | Almacenamiento |
|---|---|---|---|
| Starter | 160 $ | 50 | 1 GB |
| Mini | 250 $ | 100 | 2,5 GB |
| Small | 460 $ | 200 | 5 GB |
| Medium | 1 120 $ | 500 | 20 GB |

Para ~50 cuentas, **Starter (160 $) entra justo y Mini (250 $) da margen**.

**Pero mirad la columna de almacenamiento, que es la que decide.** 1 GB en
Starter y 2,5 GB en Mini es muy poco en cuanto entran grabaciones: 30 horas de
clase grabada no caben en ninguno de los dos planes. Hay dos salidas, y conviene
elegirla antes de contratar:

- **No grabar**, o grabar solo las conferencias invitadas.
- **Grabar y sacar los ficheros fuera**: descargarlos tras cada sesión y
  publicarlos en el servicio de vídeo institucional (CSIC, universidad) o en
  Zenodo si son abiertos, dejando en Moodle solo el enlace. Es trabajo manual,
  unos minutos al día, y resuelve el problema sin subir de plan.

Las diapositivas y cuadernos sí caben de sobra; los datos de prácticas van al
servidor de prácticas, como ya estaba previsto.

**A favor**

- Operativo el mismo día, sin servidor ni sysadmin.
- La videoconferencia viene resuelta y ya integrada: cero configuración de API.
- Copias de seguridad, actualizaciones y HTTPS incluidos.
- Soporte oficial con alguien a quien reclamar si falla durante el curso.
- Cuentas externas sin trámite — el obstáculo típico del Moodle institucional.
- Coste predecible y trivial frente al presupuesto del curso.

**En contra**

- Almacenamiento escaso, que obliga a la disciplina de arriba.
- Sin acceso al servidor: no se instalan plugins arbitrarios.
- Precio en dólares y compra internacional, con el papeleo que eso supone en
  administración pública. **Iniciadlo con margen**: puede tardar más que el
  propio despliegue técnico.

---

## Opción 3 — Zoom o Teams institucional, enlazado desde Moodle

Si el CSIC o la universidad colaboradora ya tiene licencias de Zoom o Microsoft
Teams, usarlas es tentador: coste cero y profesorado que ya las conoce.

**Zoom.** Existe el plugin `mod_zoom`, que crea las reuniones desde Moodle,
sincroniza el calendario, registra asistencia (con opción de calificar por
duración de conexión) y muestra las grabaciones en la nube dentro del aula.
Requisitos y avisos:

- Necesita una cuenta **Business o educativa** para configurarse correctamente;
  con cuentas Pro funciona, pero con acceso a API limitado.
- Usa una app OAuth servidor‑a‑servidor: alguien con permisos de administración
  en la cuenta Zoom tiene que crear las credenciales. En una cuenta
  institucional, eso significa pedirlo al servicio correspondiente.
- Hay informes de fallos puntuales en el registro de asistencia y en las
  grabaciones de sesiones pausadas: conviene no depender de esos datos para los
  ECTS sin comprobarlos.
- Las reuniones son accesibles para cualquiera con la URL **si no se pone
  contraseña**. Hay que ponerla, o usar la sala de espera.

Si no hay licencia institucional, **Zoom Pro cuesta ~170 $/año por anfitrión**
(100 participantes, sesiones de 30 h, 10 GB de grabación en la nube) y
**Business ~220 $** (300 participantes). Detalle que ahorra dinero: hace falta
una licencia **por sesión simultánea**, no por ponente. Como aquí nunca hay dos
clases a la vez, **una sola licencia basta**: la organización es la anfitriona y
cada ponente entra como coanfitrión.

**Teams** no tiene un plugin de integración tan directo como el de Zoom; lo
habitual es publicar el enlace de la reunión como recurso URL en el aula. Funciona,
pero se pierde la asistencia automática y hay que gestionar el acceso a mano.

**A favor**

- Coste cero si ya existe licencia institucional.
- Profesorado y alumnado ya saben usarlo: menos incidencias.
- Infraestructura muy fiable y con buen rendimiento en conexiones malas.
- Grabación en la nube con almacenamiento propio, fuera de la cuota de Moodle.

**En contra**

- Dependencia de otra unidad para credenciales y para cualquier incidencia.
- Orientado a reuniones, no a clases: faltan la pizarra y la vista de
  presentación de BBB, y las salas pequeñas son menos cómodas de gestionar.
- Con Teams, integración pobre: asistencia manual.
- Si la licencia es nominal de una persona, el curso depende de que esa persona
  esté disponible toda la semana.

---

## Opción 4 — BBB autoalojado

Montar nuestro propio servidor BBB. **Para este curso, no.** Los requisitos
oficiales de producción lo explican solos:

- **Ubuntu 22.04**, y únicamente esa versión.
- **8 núcleos de CPU** con buen rendimiento mono‑hilo y **16 GB de RAM**.
- **500 GB de disco** si se graban las sesiones (50 GB si no).
- **250 Mbit/s simétricos** o más.
- Puertos TCP 80/443 y **UDP 16384–32768** abiertos, IPv4 **e IPv6**, y un
  hostname con certificado.
- **Servidor dedicado**: limpio, sin otro servicio web en los puertos 80/443.

Ese último punto es el decisivo: BBB **no puede compartir máquina con Moodle**.
Autoalojar la videoconferencia significa administrar **dos** servidores, uno de
ellos exigente en CPU y red, para usarlo cinco días. Y si el ancho de banda se
queda corto durante una clase, no hay nada que hacer en caliente.

Solo tiene sentido si un centro ya opera una instancia BBB con personal que la
mantiene como parte de su trabajo. En ese caso pasa a ser, de hecho, la opción 3:
videoconferencia institucional que ya existe.

Los proveedores de BBB gestionado son una vía intermedia razonable, pero publican
sus precios **bajo consulta**, lo que añade una negociación y un contrato al
proceso. Con MoodleCloud resolviendo lo mismo a precio de catálogo, la gestión
extra no se justifica para un curso de una semana.

---

## Comparación

| | 1. BBB (servidor propio detrás) | 2. MoodleCloud + BBB | 3. Zoom/Teams institucional | 4. BBB autoalojado |
|---|---|---|---|---|
| Coste | según alojamiento | 160–250 $/año | 0 € (o ~170 $ Zoom Pro) | servidor + horas |
| 40 participantes | sí | sí (hasta 100) | sí | sí |
| Sesiones de 3,5 h | sí | sí | sí | sí |
| Integración Moodle | nativa | nativa | buena (Zoom) / pobre (Teams) | nativa |
| Asistencia automática | sí | sí | sí (Zoom) / no (Teams) | sí |
| Pensado para clase | **sí** | **sí** | no | sí |
| Grabaciones | según plan | **cuota escasa** | en la nube del proveedor | 500 GB de disco |
| Trabajo de sysadmin | medio | **ninguno** | ninguno | **alto, 2 servidores** |
| Riesgo durante el curso | medio | bajo | bajo | **alto** |

## Recomendación

**Primero preguntar, luego contratar.** Dos preguntas en paralelo, esta semana:

1. **Al CSIC o la universidad colaboradora:** ¿hay un Moodle institucional que
   admita cuentas externas con rol de Profesor, y licencia de Zoom (o Teams) que
   podamos usar para el curso? Si ambas respuestas son sí, esa es la solución:
   coste cero y responsabilidad legal ajena.

2. **A quien gestione el presupuesto:** ¿cuánto tarda una compra internacional de
   ~250 $? Esto marca el plazo real de la opción MoodleCloud, y suele ser más
   lento de lo que parece.

**Si el Moodle institucional no admite externos** —el caso más probable, y el que
hizo surgir esta pregunta— la combinación recomendada es:

> **MoodleCloud plan Mini (250 $/año) con BigBlueButton integrado**, sin grabar
> de forma sistemática, y sacando fuera del aula las grabaciones que sí se hagan.

Razones, por orden de peso:

1. **Cero administración de servidores** para un curso donde una caída no tiene
   plan B. El equipo organizador puede dedicarse al curso.
2. **La videoconferencia ya viene integrada y dimensionada** para 100 usuarios:
   nada que configurar, nada que medir.
3. **BBB está hecho para dar clase**, que es exactamente lo que son estas 30 h.
4. **250 $ es irrelevante** frente al presupuesto, y compra soporte con alguien a
   quien llamar un martes a las 10:05.

**Si existe licencia institucional de Zoom**, usarla *junto con* MoodleCloud
también es una combinación válida y nada forzada: Moodle como aula y el plugin
de Zoom para las clases. Da grabación en la nube sin tocar la cuota de Moodle y
aprovecha una herramienta que todo el mundo conoce. Se pierde la vista de
presentación de BBB, lo que importa poco si el profesorado ya se maneja con Zoom.

## Decisiones que hay que tomar (y no son técnicas)

**¿Se graban las sesiones?** Afecta a tres cosas a la vez: el consentimiento que
hay que pedir en la inscripción, el almacenamiento necesario, y lo que el
profesorado acepta. Algunos ponentes no quieren ser grabados, y es una objeción
legítima. Una vía intermedia que funciona bien: **grabar solo la parte teórica**,
nunca las prácticas ni los turnos de preguntas, donde se ven caras y se
comparten dudas. Conviene preguntárselo a cada ponente al confirmar su sesión,
no la semana antes.

Si se graba, hay que resolver antes del curso: consentimiento explícito y
separado en el formulario de inscripción; aviso visible al entrar en la sala;
plazo de conservación escrito; y quién puede ver las grabaciones (solo
inscritos, o público).

**Rellenar en `_config.yml`** cuando esté decidido:

```yaml
curso:
  videoconferencia: "BigBlueButton"   # o "Zoom"
  grabaciones: "sí"                   # o "no"
```

La página del Aula Virtual se ajusta sola: menciona la plataforma y añade el
párrafo correspondiente sobre grabaciones.

## Antes del primer día

| Cuándo | Qué | Por qué |
|---|---|---|
| −3 meses | Plataforma decidida y contratada | El papeleo de compra es el cuello de botella |
| −2 meses | Aula creada, una sala por día | |
| −6 semanas | **Prueba técnica con cada ponente** | Compartir una terminal legible para 40 personas requiere ensayo |
| −1 mes | Decidido y comunicado el asunto de las grabaciones | Entra en el formulario de inscripción |
| −1 semana | **Sala de prueba abierta a participantes** | Los problemas de audio salen aquí, no el lunes |
| −1 día | Repaso de enlaces, roles de moderador y plan B | |

Dos cosas que merecen insistencia, porque son las que fallan:

- **La prueba técnica con cada ponente.** El problema real no es la plataforma,
  es una terminal con letra de 10 px ilegible en el portátil de quien mira. Diez
  minutos por ponente lo evitan.
- **Un plan B escrito.** Si la sala no arranca: una sala alternativa ya creada
  (incluso en otra plataforma), el móvil de la persona de guardia, y un mensaje
  tipo listo para enviar al foro de avisos. Media hora de preparación que, el día
  que haga falta, salva una sesión.

## Fuentes

- Actividad BigBlueButton en Moodle, límites del servidor gratuito y cambios en 5.3: [MoodleDocs — BigBlueButton](https://docs.moodle.org/503/en/BigBlueButton)
- Planes, usuarios y almacenamiento de MoodleCloud: [MoodleCloud](https://www.moodlecloud.com/?p=75) · [MoodleCloud Plans](https://www.moodlecloud.com/?p=857)
- Requisitos de instalación de BigBlueButton: [BigBlueButton — Install](https://docs.bigbluebutton.org/administration/install/)
- Plugin de Zoom para Moodle, requisitos y limitaciones: [Moodle plugins — mod_zoom](https://moodle.org/plugins/mod_zoom)
- Planes y límites de Zoom: [Zoom pricing](https://zoom.us/pricing)

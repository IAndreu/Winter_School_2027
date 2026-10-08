# Aula Virtual: opciones de alojamiento

Documento de decisión para la Escuela de Invierno en Bioinformática Avanzada 2027.
Fecha: octubre de 2026.

> **Esta edición es 100 % en línea.** Eso sube el listón de todo lo que sigue: el
> Moodle no es un repositorio de apoyo, es el aula. Si se cae un martes a las
> 10:00 no hay plan B presencial, y la videoconferencia pasa a ser un requisito
> de primera, no un añadido. La elección de plataforma de videollamada está en
> [03-videoconferencia.md](03-videoconferencia.md) y conviene leer los dos
> documentos juntos: en la práctica se decide una sola cosa, porque la opción de
> alojamiento condiciona la de videoconferencia.

## El punto de partida

El sitio web del curso es un sitio **estático** publicado en GitHub Pages. Moodle
no puede vivir ahí: necesita PHP, una base de datos y un sistema de ficheros con
escritura. Por tanto el sitio web **enlaza** al aula virtual, no la contiene. Eso
ya está resuelto en el repositorio: la página `/aula-virtual/` y el botón de la
portada leen la variable `curso.moodle_url` de `_config.yml`, y mientras esté
vacía muestran un aviso de "próximamente" en lugar de un enlace roto.

Queda decidir **dónde se aloja el Moodle**. Hay tres caminos realistas.

## Dimensionamiento previo

Antes de comparar, conviene fijar el tamaño del problema, porque cambia mucho la
respuesta:

| Variable | Estimación para la Escuela de Invierno |
|---|---|
| Participantes | **30 máximo** |
| Profesorado + organización | 8–12 |
| **Cuentas totales** | **~40, nunca más de 50** |
| Concurrencia en videollamada | ~40, en sesiones de 3,5 h |
| Uso intensivo | 1 semana, más 2 semanas de entregas posteriores |
| Material | Diapositivas y cuadernos: cientos de MB. Datos de prácticas: en el servidor de prácticas, no en Moodle |
| Grabaciones | 30 h de clase si se graban: **decenas de GB** |
| Vida útil | La edición, más consulta posterior del material abierto |

Tres consecuencias importantes:

1. **Cuarenta cuentas es muy poco.** Entra en el escalón más barato de casi
   cualquier opción. No hay que optimizar por coste por usuario.
2. **El pico de uso es de una semana al año.** Pagar un servicio anual para
   usarlo siete días es caro por hora de uso, pero *gestionar un servidor* para
   usarlo siete días es caro en horas de persona. Esa es la tensión real, y el
   formato en línea la resuelve a favor del servicio gestionado: el día del curso
   queremos estar dando clase, no mirando logs.
3. **Las grabaciones son el único consumo de disco que importa.** Los datos de
   prácticas viven en el servidor de prácticas y las diapositivas pesan poco. Si
   se decide grabar, hay que sacar los ficheros del aula (ver el documento 03);
   si no, la cuota de almacenamiento deja de ser un criterio.

---

## Opción A — Moodle institucional (CSIC o universidad anfitriona)

Pedir un espacio de curso en un Moodle que ya existe y que alguien ya administra.

**A favor**

- Coste directo cero.
- Cero mantenimiento, copias de seguridad y actualizaciones: las hace el servicio
  de informática de la institución.
- Cumplimiento de RGPD ya resuelto por la institución, con sus encargados de
  tratamiento y sus avisos legales. Esto no es un detalle menor y es, con
  diferencia, lo más tedioso de resolver por cuenta propia.
- Autenticación institucional ya montada; posible integración con SSO.
- Continuidad entre ediciones si el curso se repite.

**En contra**

- **Altas de personas externas.** Es el verdadero obstáculo. Muchos Moodles
  institucionales solo admiten cuentas del directorio de la institución, y el
  curso tendrá participantes y ponentes de fuera. Hay que confirmar *antes* de
  comprometerse que se pueden crear cuentas externas, y con qué trámite.
- Permisos limitados: probablemente no se podrán instalar plugins, ni cambiar el
  tema, ni tocar la configuración global.
- Dependencia de los tiempos de otra unidad para cada incidencia.
- Calendario académico ajeno: ventanas de mantenimiento y cierres que no
  controlamos.
- Posible límite estricto de tamaño de fichero por subida.

**Qué hay que preguntar para poder decidir**

1. ¿Se pueden crear cuentas para personas externas a la institución? ¿Con qué
   procedimiento y plazo?
2. ¿Se puede dar el rol de *Profesor* a ponentes externos, con permiso para
   subir contenido por su cuenta?
3. **¿Qué sistema de videoconferencia hay disponible desde ese Moodle?**
   ¿BigBlueButton con servidor propio, el plugin de Zoom, Teams? ¿Soporta 40
   personas en sesiones de 3,5 horas? (Esta pregunta es nueva respecto a una
   edición presencial, y ahora es la más importante de la lista.)
4. ¿Se pueden **grabar** las sesiones? ¿Dónde se guardan las grabaciones y
   cuánto espacio hay?
5. ¿Cuál es el tamaño máximo de fichero y la cuota total del curso?
6. ¿Qué pasa con el curso al terminar? ¿Se archiva, se borra, se puede exportar?
7. ¿Hay ventanas de mantenimiento en las fechas del curso? **¿Y soporte técnico
   disponible en horario de mañana durante esa semana?**

> **Recomendación:** empezar por aquí. Una sola conversación con el servicio de
> informática del CSIC o de la universidad anfitriona resuelve o descarta esta
> opción en pocos días, y es la que menos trabajo deja. Las otras dos solo tienen
> sentido si la respuesta a la pregunta 1, la 2 o la 3 es "no".
>
> Para un curso en línea, la pregunta 3 puede descartar por sí sola un Moodle que
> cumpla todo lo demás: un aula institucional perfecta sin videoconferencia
> utilizable no nos sirve, aunque en ese caso cabe combinarla con Zoom
> institucional (ver documento 03).

---

## Opción B — MoodleCloud (alojamiento gestionado por Moodle)

El SaaS oficial. Se contrata un plan, se obtiene un sitio listo en minutos.

**Planes y precios** (facturación anual, en dólares; tarifas de octubre de 2026):

| Plan | Precio/año | Usuarios |
|---|---|---|
| Starter | 160 $ | 50 |
| Mini | 250 $ | 100 |
| Small | 460 $ | 200 |
| Medium | 1 120 $ | 500 |
| Standard | 1 970 $ | 750 |

Hay una **prueba gratuita del plan Starter**, sin tarjeta.

Con ~50 cuentas el plan **Starter (160 $/año)** encaja justo, y **Mini
(250 $/año)** da margen cómodo si la cifra de inscripciones crece o si se quiere
mantener el aula abierta a antiguos participantes. En el presupuesto de un curso
con matrícula de varios cientos de euros por persona, esto es ruido.

**A favor**

- Operativo el mismo día, sin servidor ni sysadmin.
- Copias de seguridad, actualizaciones y certificados HTTPS incluidos.
- Soporte oficial y versión siempre reciente.
- Coste predecible y fácil de justificar en un presupuesto.
- Admite cuentas externas sin trámite: el problema principal de la opción A
  desaparece.

**En contra**

- Sin acceso al servidor: no se pueden instalar plugins fuera del catálogo
  permitido ni ejecutar código propio.
- **Cuota de almacenamiento limitada.** Para un curso de bioinformática con
  datos de prácticas, es la restricción que más probablemente se note. Se
  resuelve dejando los datos pesados fuera (ver más abajo), no en el aula.
- El límite de usuarios cuenta **cuentas creadas**, no activas: si se acumulan
  ediciones, hay que ir limpiando o subir de plan.
- Precio en dólares, con el riesgo de cambio y el papeleo de una compra
  internacional, que en administración pública puede ser más lento que el propio
  despliegue.
- Dependencia de un proveedor para la exportación si algún día se migra.

---

## Opción C — Autoalojado con Docker

Un servidor propio (VPS o máquina de un centro) con Moodle en contenedores.

**Versión a usar:** **Moodle 5.3 LTS**, publicada el 5 de octubre de 2026, con
soporte general hasta octubre de 2027 y **soporte de seguridad hasta octubre de
2029**. Para un curso que se monta ahora y puede reutilizarse en ediciones
siguientes, la LTS es la elección correcta: tres años sin migraciones forzadas.

**Requisitos de Moodle 5.3:** PHP 8.3 mínimo (8.4 también soportado), con la
extensión *sodium* y PHP de 64 bits; y como base de datos PostgreSQL 17,
MySQL 8.4, MariaDB 11.4 o SQL Server 2019 como mínimos. Conviene fijarse en que
estos mínimos de base de datos **subieron** respecto a versiones anteriores: un
servidor con una MariaDB antigua no sirve sin actualizarla.

**Dimensionado sugerido** para ~50 personas concurrentes: 4 vCPU, 8 GB de RAM y
80–160 GB de disco. En un VPS europeo eso ronda los **20–40 €/mes**; si solo se
mantiene encendido tres meses alrededor del curso, son **60–120 €** por edición.

**A favor**

- Control completo: cualquier plugin, cualquier tema, cualquier integración.
- Sin límite de usuarios ni de almacenamiento más allá del disco contratado.
- Se puede colocar junto al servidor de prácticas, en la misma red.
- Los datos quedan donde nosotros decidamos, lo que simplifica algunas
  discusiones de protección de datos (y complica otras: ver abajo).
- Barato si ya existe infraestructura disponible en un centro.

**En contra**

- **Alguien tiene que administrarlo, y ese alguien tiene nombre.** Este es el
  coste real y el que se subestima siempre. Actualizaciones de seguridad,
  certificados, copias de seguridad probadas, cuota de disco, correo saliente.
- **El correo saliente es el punto donde más se tropieza.** Moodle necesita
  enviar avisos de alta y recuperación de contraseña; un VPS nuevo tiene una
  reputación de IP nula y sus correos acaban en spam. Hay que usar un SMTP
  externo (el institucional, o un servicio transaccional) desde el principio,
  no el día antes del curso.
- Responsabilidad legal propia: RGPD, aviso de privacidad, registro de
  actividades de tratamiento, y respuesta ante una brecha.
- Un Moodle público sin mantener es un riesgo de seguridad real, no teórico. Si
  se levanta, hay que planificar también **cómo se apaga**.

---

## Comparación resumida

| | A — Institucional | B — MoodleCloud | C — Autoalojado |
|---|---|---|---|
| Coste directo | 0 € | ~160–250 $/año | ~60–120 € por edición, **más el servidor de BBB** |
| Coste en horas de persona | Muy bajo | Bajo | **Alto y continuado** |
| Tiempo hasta estar operativo | Días o semanas (trámite) | Horas | 1–3 días + mantenimiento |
| Cuentas externas | **Incierto — verificar** | Sin problema | Sin problema |
| **Videoconferencia** | **Incierto — verificar** | **Incluida, hasta 100 usuarios** | Segundo servidor dedicado |
| Control y plugins | Bajo | Medio | Total |
| Almacenamiento | Según institución | Escaso (1–2,5 GB) | Según disco |
| RGPD | Resuelto | Del proveedor + nuestro | **Nuestro** |
| Riesgo principal | Que no admitan externos o no haya videollamada | Cuota de disco | Que nadie lo mantenga, **y ahora por duplicado** |

---

## Recomendación

**Un camino en dos pasos, no una elección única.**

1. **Preguntar primero por la opción A**, con las siete preguntas de arriba. Es
   gratis, no compromete a nada y en pocos días se sabe si es viable. Si admite
   cuentas externas con rol de Profesor **y tiene videoconferencia utilizable**,
   es la mejor opción por mucho: elimina el coste y la responsabilidad legal.

   Una variante que conviene tener presente: un Moodle institucional que admita
   externos pero sin videollamada decente **sigue sirviendo** si la institución
   tiene licencia de Zoom. Aula institucional + Zoom institucional = coste cero.

2. **Si la A no sirve, ir a MoodleCloud Mini.** Para un curso en línea de una
   semana con 40 personas, 250 $ al año compran el aula **y la videoconferencia
   integrada para hasta 100 usuarios**, y evitan el único riesgo que de verdad
   puede estropear el curso: que la persona que administra el servidor no esté
   disponible el lunes por la mañana. Siendo el curso en línea, ese riesgo ya no
   afecta solo al material: afecta a que la clase ocurra.

3. **La opción C, prácticamente descartada para esta edición.** Antes era una
   alternativa razonable si había infraestructura disponible. Ahora implica
   administrar **dos** servidores —Moodle y un BBB dedicado de 8 núcleos, 16 GB y
   250 Mbit/s simétricos, que no puede compartir máquina— para usarlos cinco
   días. Solo tiene sentido si un centro **ya opera** una instancia BBB con
   personal propio, caso en el que estamos de hecho en la opción A.

**Y en los tres casos, la misma regla sobre los datos:** los conjuntos de datos
de prácticas **no** se suben al Moodle. Van a Zenodo, a un bucket, o al servidor
de prácticas donde de todos modos se van a analizar, y en el aula solo se pone
el enlace y el checksum. Al ser el curso en línea esto deja de ser solo una
cuestión de cuota: nadie va a descargar 2 GB por una conexión doméstica antes de
una práctica. El dato se queda donde se analiza.

Lo mismo para las **grabaciones**, que son el nuevo consumidor de disco: si se
graban, se descargan tras cada sesión y se publican en el servicio de vídeo
institucional, dejando en Moodle solo el enlace.

## Plazos

Contando hacia atrás desde el inicio del curso:

| Cuándo | Qué |
|---|---|
| −4 meses | Decidir alojamiento **y videoconferencia** (preguntar a la institución ya) |
| −3 meses | Aula creada, estructura de secciones montada, una sala por día |
| −2 meses | Altas del profesorado y guía enviada |
| −6 semanas | Ponentes suben material teórico · **prueba técnica con cada ponente** |
| −1 mes | Altas de participantes, correo de bienvenida · decidido el tema de grabaciones |
| −1 semana | **Sala de prueba abierta** a participantes (audio, cámara, servidor) |
| −1 día | Repaso de enlaces, roles de moderador y plan B escrito |
| +2 semanas | Cierre de entregas, exportación y archivado |

Las dos filas en negrita son nuevas respecto a una edición presencial y son las
que más incidencias evitan. El detalle está en
[03-videoconferencia.md](03-videoconferencia.md).

## Fuentes

- Planes y precios de MoodleCloud: [MoodleCloud](https://www.moodlecloud.com/?p=75)
- Calendario de versiones y fechas de soporte: [Moodle Developer Resources — Releases](https://moodledev.io/general/releases)
- Requisitos de servidor de Moodle 5.3: [Moodle 5.3 release notes](https://moodledev.io/general/releases/5.3)

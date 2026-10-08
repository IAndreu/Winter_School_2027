# Guía para el profesorado

Esta guía explica **dónde va cada cosa**, **cómo subir tu material** y **cómo dar
tu sesión en línea** en la Escuela de Invierno en Bioinformática Avanzada 2027.

> **Esta edición es 100 % en línea.** Tu sesión se imparte por videoconferencia
> desde el Aula Virtual, con un grupo de **30 participantes como máximo**. La
> sección 6 recoge lo que conviene preparar de forma distinta a una clase
> presencial; si solo vas a leer un apartado, que sea ese.

Hay dos destinos posibles, y la regla para elegir es sencilla:

| Lo que quieres publicar | Dónde va | Por qué |
|---|---|---|
| Diapositivas, guiones de prácticas, cuadernos, scripts de acceso abierto | **Este repositorio** (`materials/`) | Queda público y citable para siempre, también cuando el aula se cierre |
| Datos de ejemplo grandes (> 50 MB) | **Aula Virtual** o repositorio de datos (Zenodo) | GitHub rechaza ficheros grandes |
| Material con licencia restrictiva o de terceros | **Aula Virtual** | Acceso limitado a personas inscritas |
| Tareas evaluables, foros, encuestas, notas | **Aula Virtual** | Necesita identificación y seguimiento |
| Datos personales o sensibles | **Aula Virtual**, nunca aquí | Un repositorio público no es el sitio |

---

## 1. Tu carpeta en el repositorio

Cada ponente tiene su propia carpeta dentro del día que le corresponde:

```
materials/
  day1/
  day2/
    apellido-tema/          <- tu carpeta
      README.md             <- describe la sesión (plantilla incluida)
      slides/
      practicas/
      datos/
```

Nómbrala en minúsculas, con guiones y sin acentos: `bombarely-ensamblado`,
`conesa-long-reads`. Dentro mandas tú: organiza las subcarpetas como prefieras,
pero mantén el `README.md` en la raíz de tu carpeta.

### Qué poner en el README

Hay una plantilla en [`materials/_plantilla-ponente/README.md`](materials/_plantilla-ponente/README.md).
Cópiala a tu carpeta y rellénala. Como mínimo debe decir: de qué va la sesión,
qué software hace falta, en qué orden se usan los ficheros, y la licencia de tu
material.

---

## 2. Cómo subir el material

### Opción A — desde la web de GitHub (sin usar git)

Es la vía más rápida si no trabajas habitualmente con git:

1. Entra en el repositorio y abre la carpeta de tu día, p. ej. `materials/day2/`.
2. **Add file › Upload files**, arrastra tus ficheros.
3. Para crear tu carpeta, en **Add file › Create new file** escribe
   `apellido-tema/README.md` — la barra crea la carpeta automáticamente.
4. Abajo, escribe una descripción breve del cambio y pulsa **Commit changes**.

Si no tienes permiso de escritura, GitHub te ofrecerá crear un *fork* y una
*pull request*: acéptalo, y la organización la revisará y fusionará.

### Opción B — con git en tu ordenador

```bash
git clone https://github.com/ConexionBCB/Winter_School_2027.git
cd Winter_School_2027

git checkout -b material-apellido          # una rama por ponente
mkdir -p materials/day2/apellido-tema
cp -r ~/mis-diapositivas/* materials/day2/apellido-tema/

git add materials/day2/apellido-tema
git commit -m "Material de la sesión de [tema]"
git push -u origin material-apellido
```

Después abre una *pull request* desde la web de GitHub. Trabajar en una rama
propia evita conflictos cuando varias personas suben material a la vez.

### Reglas prácticas

- **Nada de ficheros de más de 50 MB.** GitHub avisa a partir de 50 MB y
  rechaza a partir de 100 MB. Los datos grandes van al Aula Virtual o a Zenodo,
  y en tu README pones el enlace y el checksum.
- **Sin acentos ni espacios en los nombres de fichero.** `practica-01.ipynb`,
  no `Práctica 1 (final).ipynb`.
- **Limpia la salida de los cuadernos** antes de subirlos
  (`jupyter nbconvert --clear-output --inplace tu-cuaderno.ipynb`): pesan mucho
  menos y el historial queda legible.
- **PDF mejor que PPTX** para las diapositivas que se publiquen, salvo que
  quieras que se puedan editar.
- **Indica la licencia** de tu material en tu README. Si no indicas nada se
  asume que mantienes todos los derechos, lo que impide reutilizarlo en
  docencia — y ese es justamente el objetivo del curso.

---

## 3. Tu sección en el Aula Virtual (Moodle)

Cada ponente recibe el rol de **Profesor** sobre su propia sección, de modo que
puedas subir y reorganizar tu material sin pedir permiso a nadie. Ese mismo rol
te da permiso de **moderador en la sala de videoconferencia** de tu día.

1. Acepta la invitación que recibirás por correo y entra en el aula.
2. Busca tu sección: **Día N — Tu nombre**. Arriba encontrarás ya creada la
   actividad **▶ Sesión en directo**: es por donde entrarás a dar tu clase, y por
   donde entra el grupo. No hace falta que la crees ni que generes ningún enlace.
3. Arriba a la derecha, activa **Modo de edición**.
4. **Añadir una actividad o recurso** y elige:
   - **Archivo** — diapositivas, PDF, un cuaderno suelto.
   - **Carpeta** — un conjunto de ficheros que se descargan juntos.
   - **URL** — enlaces a GitHub, Colab, Zenodo o tu propia web.
   - **Página** — instrucciones escritas directamente en Moodle.
   - **Tarea** — si tu sesión tiene entrega evaluable (pon fecha límite).
   - **Foro** — dudas específicas de tu sesión.
5. Arrastra los elementos para ordenarlos dentro de tu sección.

**Plazo:** deja visible el material teórico **al menos una semana antes** de tu
sesión, para que quien quiera pueda prepararla. El material de prácticas puede
publicarse el mismo día, pero en una edición en línea conviene subirlo también
con antelación: mucha gente sigue la clase con las diapositivas abiertas en una
segunda pantalla.

**Un atajo útil:** puedes arrastrar ficheros directamente desde tu escritorio a
la sección con el modo de edición activado; Moodle crea el recurso *Archivo*
automáticamente.

---

## 4. Dar tu sesión en línea

Esto es lo que cambia respecto a una clase presencial. Nada aquí es complicado,
pero casi todo se descubre tarde si no se prepara.

### La prueba técnica (no te la salte)

La organización te propondrá una **prueba de 10–15 minutos** unas seis semanas
antes. Sirve para comprobar audio, compartir pantalla y, si las vas a usar, las
salas pequeñas. El problema que aparece siempre no es la plataforma: es que **la
terminal o el IDE se ven ilegibles** al otro lado.

### Que se vea tu terminal

Compartir una terminal para 30 personas que miran en portátiles, algunas en
pantallas de 13 pulgadas, exige preparación:

- **Letra grande, mucho más de la que te resulta cómoda a ti.** Como referencia,
  entre 16 y 20 pt en una pantalla de 1080p. Pruébalo mirando la miniatura de tu
  propia pantalla compartida: si tú no lo lees ahí, nadie lo lee.
- **Tema claro** (fondo blanco, texto oscuro). Aguanta mucho mejor la compresión
  de vídeo y las pantallas mal calibradas que un tema oscuro.
- **Comparte solo una ventana**, no el escritorio completo. Evita enseñar correo,
  notificaciones o nombres de ficheros que no toca.
- **Ventana estrecha y alta** antes que ancha: el texto que se parte en dos
  líneas es difícil de seguir.
- Si usas Jupyter o RStudio, **aumenta el zoom del navegador** (Ctrl/Cmd + +) en
  lugar de confiar en el tamaño por defecto.
- Silencia notificaciones del sistema antes de empezar.

### Ritmo y participación

Seguir tres horas y media de clase por videollamada cansa más que en persona, y
la atención se pierde sin que te des cuenta porque no ves las caras del fondo.

- **Pausas de 5 minutos cada 60–75 minutos.** Están en el horario; úsalas.
- **Pregunta explícitamente.** "¿Alguna duda?" por videollamada suele recibir
  silencio. Funciona mucho mejor algo concreto: "poned en el chat qué os ha
  devuelto el comando", o "levantad la mano quien ya tenga el fichero generado".
- **Marca los puntos de control** en las prácticas: momentos donde todo el grupo
  debe tener el mismo resultado antes de seguir. Sin ellos, en línea es
  imposible saber si alguien se ha quedado atrás hace veinte minutos.
- **Aprovecha el chat.** Pega ahí los comandos largos en lugar de dictarlos: se
  copian y evitas erratas. Alguien de la coordinación estará atento al chat
  mientras tú explicas.
- **Salas pequeñas:** si en una práctica se atascan tres o cuatro personas, se
  pueden llevar a una sala aparte para ayudarlas sin detener al resto. Dilo en la
  prueba técnica si quieres usarlas.

### Material pensado para pantalla

- **Envía las diapositivas al aula antes de la sesión**, no después. Mucha gente
  las sigue en su segunda pantalla mientras tú hablas.
- En el guion de prácticas, **numera los pasos** y pon los comandos en bloques
  copiables. En línea, "como hicimos antes" no funciona: la gente se reincorpora
  a mitad.
- Incluye el **resultado esperado** de cada paso clave ("deberías ver 4 ficheros
  .bam"), para que cada persona compruebe por sí misma que va bien.

### Grabaciones

La organización decidirá si se graban las sesiones y te lo preguntará al
confirmar la tuya. **Puedes negarte**, y es una posición perfectamente legítima.
Si se graba, lo habitual será grabar solo la parte teórica, no las prácticas ni
los turnos de preguntas.

### Si algo falla

- Entra **10 minutos antes** de tu hora.
- Habrá una persona de la coordinación con rol de moderador en tu sala y un
  teléfono de contacto para incidencias; lo recibirás antes del curso.
- Si se te cae la conexión, no improvises: la coordinación avisa al grupo por el
  foro y reanudáis. Está previsto.

## 5. Requisitos de software para las prácticas

Si tu sesión necesita software concreto en el servidor de prácticas, comunícalo
a la organización **con un mes de antelación**, indicando:

- Paquetes y versiones (idealmente un `environment.yml` de conda o un
  `requirements.txt`, o una imagen de contenedor).
- Recursos: memoria y CPU aproximados por participante.
- Datos que haya que precargar y su tamaño.

Escribe a **conexion-bcb@csic.es** con el asunto `[Escuela Invierno 2027] Software`.

---

## 6. A quién preguntar

- **Dudas sobre el repositorio o el sitio web:** abre una *issue* en GitHub.
- **Dudas sobre el Aula Virtual o problemas de acceso:** conexion-bcb@csic.es
- **Dudas sobre el programa o los horarios:** contacta con la coordinación.

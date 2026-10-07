# Guía para el profesorado

Esta guía explica **dónde va cada cosa** y **cómo subir tu material** para la
Escuela de Invierno en Bioinformática Avanzada 2027.

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
puedas subir y reorganizar tu material sin pedir permiso a nadie.

1. Acepta la invitación que recibirás por correo y entra en el aula.
2. Busca tu sección: **Día N — Tu nombre**.
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
publicarse el mismo día.

**Un atajo útil:** puedes arrastrar ficheros directamente desde tu escritorio a
la sección con el modo de edición activado; Moodle crea el recurso *Archivo*
automáticamente.

---

## 4. Requisitos de software para las prácticas

Si tu sesión necesita software concreto en el servidor de prácticas, comunícalo
a la organización **con un mes de antelación**, indicando:

- Paquetes y versiones (idealmente un `environment.yml` de conda o un
  `requirements.txt`, o una imagen de contenedor).
- Recursos: memoria y CPU aproximados por participante.
- Datos que haya que precargar y su tamaño.

Escribe a **conexion-bcb@csic.es** con el asunto `[Escuela Invierno 2027] Software`.

---

## 5. A quién preguntar

- **Dudas sobre el repositorio o el sitio web:** abre una *issue* en GitHub.
- **Dudas sobre el Aula Virtual o problemas de acceso:** conexion-bcb@csic.es
- **Dudas sobre el programa o los horarios:** contacta con la coordinación.

# Documentación del Aula Virtual (Moodle)

Notas de trabajo para la organización. **No se publica en el sitio web**: la
carpeta `docs/` está excluida en `_config.yml`.

> **Esta edición es 100 % en línea**, con un máximo de 30 participantes (~40
> cuentas en total). El Moodle no es un repositorio de apoyo: es el aula, y la
> videoconferencia es un requisito de primera.

| Documento | Contenido |
|---|---|
| [01 — Opciones de alojamiento](01-opciones-de-alojamiento.md) | Comparación de las tres vías (institucional, MoodleCloud, autoalojado), costes, riesgos y recomendación |
| [02 — Estructura del aula](02-estructura-del-aula.md) | Secciones, roles, permisos por ponente, moderación de salas, inscripciones, RGPD y cierre de la edición |
| [03 — Videoconferencia](03-videoconferencia.md) | **Elección de plataforma para las clases en directo**: BigBlueButton, MoodleCloud, Zoom/Teams institucional, autoalojado |
| [plantilla-usuarios.csv](plantilla-usuarios.csv) | Fichero de ejemplo para el alta masiva de participantes |

Los documentos 01 y 03 se leen juntos: en la práctica se decide **una sola cosa**,
porque el alojamiento condiciona la videoconferencia disponible.

## Resumen de la recomendación

1. **Preguntar al CSIC / universidad colaboradora / CRAG** (siete preguntas en el doc 01):
   ¿Moodle institucional con cuentas externas, rol de Profesor **y
   videoconferencia para 40 personas en sesiones de 3,5 h**? ¿Hay licencia de
   Zoom institucional?
2. **Si no:** MoodleCloud plan Mini (250 $/año, 100 usuarios) con BigBlueButton
   integrado, sin grabar de forma sistemática.
3. **Autoalojar: no** en esta edición. Exigiría dos servidores, uno de ellos un
   BBB dedicado de 8 núcleos y 250 Mbit/s simétricos, para cinco días de uso.

## Estado de la decisión

- [ ] Preguntar por un Moodle institucional **y por videoconferencia disponible**
- [ ] Comprobar si hay licencia institucional de Zoom o Teams
- [ ] Averiguar plazos de una compra internacional de ~250 $ (suele ser el cuello
      de botella real)
- [ ] Decidir alojamiento y plataforma de videollamada
- [ ] **Decidir si se graban las sesiones** y preguntar al profesorado
- [ ] Crear el aula, montar las secciones y una sala por día
- [ ] Rellenar `moodle_url`, `videoconferencia` y `grabaciones` en `_config.yml`
- [ ] Dar de alta al profesorado y enviarles `CONTRIBUTING.md`
- [ ] Prueba técnica con cada ponente (−6 semanas)
- [ ] Dar de alta a participantes
- [ ] Abrir la sala de prueba a participantes (−1 semana)
- [ ] Escribir el plan B para caídas durante el curso

## Lo único que hay que tocar en el sitio web

Cuando esté decidido, editar en `_config.yml`:

```yaml
curso:
  moodle_url: "https://..."
  videoconferencia: "BigBlueButton"   # o "Zoom"
  grabaciones: "sí"                   # o "no"
```

Eso activa el botón de acceso en la portada y en la página *Aula Virtual*, y
añade los párrafos correspondientes sobre plataforma y grabaciones. Mientras
estén vacíos o en `[TBC]`, las páginas muestran avisos de "próximamente" y
omiten esos detalles. No hay que editar ninguna página.

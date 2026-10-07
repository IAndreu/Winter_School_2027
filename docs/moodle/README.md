# Documentación del Aula Virtual (Moodle)

Notas de trabajo para la organización. **No se publica en el sitio web**: la
carpeta `docs/` está excluida en `_config.yml`.

| Documento | Contenido |
|---|---|
| [01 — Opciones de alojamiento](01-opciones-de-alojamiento.md) | Comparación de las tres vías (institucional, MoodleCloud, autoalojado), costes, riesgos y recomendación |
| [02 — Estructura del aula](02-estructura-del-aula.md) | Secciones, roles, permisos por ponente, inscripciones, RGPD y cierre de la edición |
| [plantilla-usuarios.csv](plantilla-usuarios.csv) | Fichero de ejemplo para el alta masiva de participantes |

## Estado de la decisión

- [ ] Preguntar al servicio de informática del CSIC / universidad anfitriona por
      un espacio de curso (ver las cinco preguntas del documento 01)
- [ ] Decidir alojamiento
- [ ] Crear el aula y montar la estructura de secciones
- [ ] Rellenar `curso.moodle_url` en `_config.yml` → el enlace aparece solo
- [ ] Dar de alta al profesorado y enviarles `CONTRIBUTING.md`
- [ ] Dar de alta a participantes

## Lo único que hay que tocar en el sitio web

Cuando el aula exista, editar en `_config.yml`:

```yaml
curso:
  moodle_url: "https://..."
```

Eso activa el botón de acceso en la portada y en la página *Aula Virtual*.
Mientras esté vacío, ambas muestran un aviso de "próximamente". No hay que
editar ninguna página.

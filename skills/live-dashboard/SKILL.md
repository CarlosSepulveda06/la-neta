---
name: "live-dashboard"
description: "En construcción: resumen matutino automático con calendario, correos y pendientes del día."
---

# Skill: Live Dashboard — EN CONSTRUCCIÓN

## Idea general
Un **resumen matutino** que el usuario recibe al empezar el día, consolidando en un solo lugar:

1. **Calendario** — eventos de hoy (Google Calendar, Outlook, .ics local)
2. **Correos prioritarios** — no leídos / marcados / de contactos clave (Gmail, Outlook, IMAP)
3. **Pendientes / tareas** — de apps compatibles (Todoist, Things, Obsidian tasks, Notion, GitHub Issues, Linear)

Todo renderizado en Markdown limpio, listo para leer en terminal o copiar a Notion/Obsidian.

---

## Qué NO hace (por ahora)
- No envía notificaciones push
- No escribe en calendarios ni borra correos
- No reemplaza a tu app de tareas

---

## Próximos pasos (borrador)
- [ ] Definir fuentes de datos configurables (YAML local)
- [ ] Plantilla de salida Markdown con secciones colapsables
- [ ] Filtros: "solo reuniones", "solo tareas vencidas hoy", "correos de X dominio"
- [ ] Comando para generar el resumen (por definir)
- [ ] Opcional: integración con `cuestionario-estilo` para redactar el resumen *con tu voz*

---

## Estado actual
**Solo especificación.** El código llegará en próximas versiones del plugin.

¿Ideas? Abre un issue o PR en el repo.

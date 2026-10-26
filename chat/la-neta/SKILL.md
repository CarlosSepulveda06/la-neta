---
name: la-neta
description: Cuestionario de estilo en español (enfoque mexicano). Úsala cuando el usuario diga "hazme el cuestionario de estilo" o quiera que la IA escriba con su voz. Lo entrevista, analiza textos suyos y le genera su skill personal "mi-voz" lista para subir.
---

# la-neta (versión para chat)

Sirve en el chat de Claude y en ChatGPT con skills. Hace la entrevista y al final le entrega al usuario **su propia skill personal** (`mi-voz.zip`) con su perfil adentro. Esa skill es la que después escribe con su voz.

## Paso 1 — Entrevista
- Preguntas cortas, por tandas. **Máximo 2 preguntas por mensaje.** Espera respuesta antes de seguir.
- Tandas:
  1. Cómo quiere sonar y qué no quiere parecer.
  2. De dónde es, modismos y muletillas (ej.: *qué onda, la neta, órale, simón, nel, ahorita, ándale*; se adapta a cualquier país).
  3. Cómo saluda, se despide y firma según con quién habla (amigos, familia, clientes o trabajo, escuela).
  4. Palabras y frases que odia o nunca usaría.
  5. Qué tan formal es (1 a 5) con amigos, familia, clientes/trabajo y escuela.
  6. Temas o referencias que usa seguido.

## Paso 2 — Textos reales
Pide de 3 a 5 textos suyos y variados: un chat con amigos, un mensaje de trabajo, un correo o trabajo de escuela. Pídele que **borre antes datos sensibles** (direcciones, números de cuenta, contraseñas, datos de otras personas).

Si lo que dijo en la entrevista choca con lo que escribe de verdad, **manda lo que escribe**.

## Paso 3 — Armar el perfil
Escribe el perfil con estas secciones, en máximo ~2,500 caracteres:
Resumen / Saludos y firma por registro / Informal (amigos y familia) / Semiformal (clientes, trabajo) / Formal (escuela, trámites) / Muletillas reales / Errores típicos a corregir en formal / Lista negra.

**Solo estilo.** Nada de nombres, lugares, fechas ni hechos de sus textos.

## Paso 4 — Generar su skill personal
1. Lee `plantilla-mi-voz.md` (está junto a este archivo).
2. Copia su contenido y reemplaza `{{PERFIL}}` por el perfil del paso 3 y `{{TRATO}}` por cómo quiere que le digan (su nombre o apodo).
3. Guárdalo como `mi-voz/SKILL.md` y comprime la carpeta `mi-voz` en `mi-voz.zip`. Si no puedes crear archivos, entrégale el texto completo en un bloque de código.
4. Dale el archivo para descargar y dile:
   - **Claude:** Ajustes → Capacidades → Skills → "Upload skill" → sube `mi-voz.zip`.
   - **ChatGPT (con skills):** súbelo desde la sección de habilidades.
   - Desde ahí, cuando pida redactar algo, le va a preguntar *"¿Lo escribo como tú o a mi manera?"*.
   - Puede desactivar la-neta y volver a activarla cuando quiera actualizar su perfil.

## Privacidad (dilo así al terminar)
*"Tu perfil va dentro de tu skill personal, en tu cuenta. Cuando la IA escribe algo por ti, lo lee como contexto, igual que cualquier mensaje. No pongas datos sensibles en él."*

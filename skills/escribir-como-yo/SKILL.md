---
name: "escribir-como-yo"
description: "Úsala SIEMPRE que el usuario pida redactar, escribir, reescribir, corregir, contestar o mejorar cualquier texto que vaya a mandar o entregar: correos, mensajes de WhatsApp, posts, trabajos de escuela, cartas, avisos, respuestas a clientes. Pregunta si lo escribe con el estilo del usuario (perfil de la-neta) o al estilo de Claude, y aplica el perfil cuando toque."
---

# Skill: Escribir como yo

## Cuándo se usa
Cada vez que el usuario pida un texto que **va a mandar o entregar como suyo**: "redacta", "escríbeme", "contéstale", "reescribe", "mejora este correo", "hazme el mensaje", etc.

No aplica a código, comentarios de código, documentación técnica ni respuestas que son para el propio usuario (explicaciones, resúmenes que solo va a leer él).

## Paso 1 — Buscar el perfil
Lee `~/.claude/la-neta/mi-perfil.md` (en Windows: `%USERPROFILE%\.claude\la-neta\mi-perfil.md`).

- **Si no existe:** escribe el texto normal y al final ofrece en una línea: *"¿Quieres que la próxima vez suene a ti? Corre /la-neta:cuestionario-estilo y armamos tu perfil."*
- **Si existe:** sigue al paso 2.

## Paso 2 — Preguntar (solo si hace falta)
Antes de escribir, pregunta en una línea corta, usando el apodo o forma de trato que el perfil diga que le gusta (si no hay, usa su nombre):

> *"¿Lo escribo como tú o a mi manera, [apodo]?"*

**No preguntes** si:
- El usuario ya lo dijo ("con mi estilo", "como yo", "a tu manera", "tú escríbelo normal").
- Ya contestó esa pregunta en esta sesión **para el mismo tipo de texto**. Vuelve a preguntar solo si cambia el registro (ej: de mensaje a un compa → trabajo de escuela).

## Paso 3 — Escribir
- **"Como yo":** aplica el perfil completo y las reglas por registro de abajo.
- **"A tu manera":** escribe claro y natural, sin el perfil, pero respetando la lista negra del perfil (sección "Lo que NUNCA debe aparecer").

Si el registro no es obvio (¿es para un amigo o para un cliente?), pregúntalo junto con la pregunta del paso 2, en el mismo mensaje.

## Reglas por registro (obligatorias)
Las muletillas y modismos del perfil **no van en todos lados**:

| Nivel | Contextos típicos | Muletillas y modismos | Faltas de dedo / ortografía |
|---|---|---|---|
| 1–2 | Amigos, familia cercana | Sí, los del perfil | Se pueden imitar si el usuario lo pide |
| 3 | Conocidos, compañeros, clientes, inquilinos | Solo los suaves (ej: "ahorita", "quedo pendiente") | Corregidas |
| 4–5 | Escuela, trabajos académicos, jefes, trámites | **Ninguno.** Nada de "pues", "la verdad", "creo yo", "o sea", "la neta", "tipo", "wey" | Corregidas |

En niveles 4–5 la voz del usuario se nota en **qué** dice y **cómo arma las ideas** (vocabulario sencillo, primera persona, ejemplos concretos), no en muletillas.

**Largo de oraciones:** en niveles 3–5, ninguna oración pasa de ~35 palabras. Si escribir largo con comas es rasgo del usuario, respétalo partiendo en dos o tres oraciones conectadas.

**Saludos, despedidas y firma:** usa los del perfil para ese registro.

## Paso 4 — Revisar antes de entregar (obligatorio)
Antes de mostrar el texto, revísalo contra esta lista y corrige lo que falle. No le enseñes la lista al usuario; solo entrega el texto ya corregido.

1. **Coherencia con la situación.** Cada frase tiene que tener sentido para *este* mensaje. Las frases del perfil son ejemplos del estilo, no plantillas para pegar: si el usuario escribe primero, no agradezcas "que se haya comunicado"; si avisa algo, no respondas como si contestara.
2. **Un solo saludo y una sola despedida.** Nada de dos cierres seguidos ("Muchas gracias… / ¡Buen día!"). Si el saludo dice "buen día", la despedida no lo repite.
3. **Ortografía en niveles 3–5:** acentos (*qué, cómo, cuándo* en preguntas y exclamaciones; *día, entregaré*), signos de apertura (**¡** y **¿**) y mayúsculas al inicio. En niveles 1–2 respeta cómo escribe el usuario.
4. **Datos ambiguos: pregunta, no supongas.** Si una hora no dice a.m./p.m., una fecha no dice el día o falta un nombre, pregúntalo en la misma línea donde pides los demás datos. Si ya escribiste el texto, márcalo con `[confirmar]` y avísale.
5. **Nada inventado.** Ningún motivo, dato, promesa, medio de entrega o compromiso que el usuario no haya dicho. **Avisarlo después no lo arregla:** si falta un dato, pregúntalo antes de escribir o déjalo fuera.
6. **Saludo según la hora.** Si el usuario dijo cuándo lo va a mandar, usa *buenos días / buenas tardes / buenas noches* según corresponda; si no lo sabes, usa un saludo neutro del perfil (ej: *"Qué tal, profesor"*).

### Ejemplos de la revisión (niveles 3–5)
Las frases y saludos del perfil vienen de chats reales, con su ortografía de chat. **En niveles 3–5 se corrigen siempre**, aunque el perfil las tenga escritas así.

**Ortografía del saludo**
- ❌ `Que tal profesor, buen dia.`
- ✅ `Qué tal, profesor, buen día.`

**Signos de exclamación**
- ❌ `Muchas gracias por su comprensión!`
- ✅ `Muchas gracias por su comprensión.` (en formal, mejor sin exclamación; si la llevas, siempre con `¡…!`)

**Una sola despedida, sin repetir el saludo**
- ❌ `Que tal…, buena noche.` … `Muchas gracias por su comprensión! Buena noche!`
- ✅ `Qué tal…, buenas noches.` … `Muchas gracias por su comprensión.` + firma

**No agregar datos, aunque los avises después**
- ❌ `…la voy a subir a la plataforma.` (el usuario nunca dijo cómo la entrega) y luego "Puse que la subes a la plataforma, dime si no"
- ✅ Omitir ese dato. Si hace falta para que el texto tenga sentido, **pregúntalo antes de escribir**.

**No repetir la misma idea**
- ❌ `Hoy entrego la actividad… Igual le comento que la voy a subir el día de hoy…`
- ✅ `Le aviso que hoy entregaré la actividad 3 fuera de tiempo, aproximadamente a las 11:30 p.m.`

**Tratamiento**
- ❌ `Qué tal, Ramírez,` (nombre pelón a un profesor)
- ✅ `Qué tal, profesor Ramírez,` — si no sabes si es profesor o profesora, pregúntalo junto con los demás datos.

Después de revisar, **vuelve a leer el texto completo una vez más** buscando solo estas seis cosas. Si encuentras una, corrígela antes de mostrarlo.

## Reescribir documentos
- Conserva datos, cifras, calificaciones, citas y referencias tal cual. No inventes hechos.
- Guarda el resultado como **archivo nuevo** y nunca sobrescribas el original.
- Al terminar, di en una línea qué registro usaste (ej: *"Lo dejé en registro escolar, sin muletillas"*).

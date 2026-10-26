---
name: "cuestionario-estilo"
description: "Úsala cuando quieras que Claude escriba con tu voz: te entrevista, analiza tus textos y crea un perfil local que consulta al redactar. Enfoque mexicano (norte, frontera, chilango, etc.) pero sirve para cualquier hispanohablante."
---

# Skill: Cuestionario de Estilo de Escritura

## Objetivo
Entrevistar al usuario para crear un perfil de su forma de escribir, de modo que los textos generados suenen como **él/ella** y no como IA. El perfil se guarda en `~/.claude/la-neta/mi-perfil.md` y la IA lo consulta cada vez que redacte algo por ti.

> **Privacidad honesta:** el archivo **nunca se sube a GitHub** ni sale de tu carpeta de usuario. Pero cuando la IA lo usa para escribir, **lo lee como contexto** (viaja al proveedor de la IA igual que cualquier mensaje que le mandes). **No pongas datos sensibles** (contraseñas, direcciones, números de cuenta, claves, tokens) en el perfil.

---

## Flujo de la entrevista

### Regla de oro
**Preguntas cortas, por tandas, nunca todas de golpe.** Espera respuesta antes de pasar a la siguiente tanda. **Máximo 2 preguntas por mensaje, sin excepción.** Si una tanda tiene 3 preguntas, pártela en dos mensajes.

---

### Tanda 1 — Valores y percepción
> *Entender qué quieres proyectar.*
1. ¿Qué tres adjetivos quieres que la gente asocie a tu forma de escribir? (ej: cercano, directo, irónico, con chispa)
2. ¿Qué **no** quieres que parezca? (ej: robótico, muy formal, vendedor, pretencioso, "escrito por IA")

---

### Tanda 2 — Modismos, regionalismos y muletillas
> *Capturar tu sabor local.*
1. ¿De qué región/país eres? (México: norte, frontera, chilango, bajío, occidente, sureste; Cono Sur, Caribe, España, etc.)
2. ¿Qué modismos o palabras "tuyas" usas mucho? (ej: *órale, chido, qué onda, güey/wey, simón, nel, ahorita, ándale, qué pedo, fierro, arre, a huevo* cuando hay confianza, *chale, no manches, está cañón, poca madre*)
3. ¿Tienes muletillas al escribir? (ej: *pues, o sea, tipo, este..., la neta, en plan, mira, fíjate*)

---

### Tanda 3 — Saludos, despedidas y firma
> *El marco de cada mensaje.*
1. ¿Cómo saludas y cómo te despides? ¿Cambia si es un compa, la familia o la escuela? (ej: *Qué onda / Qué tal, buen día / Buenas* … *Arre, Fierro / Saludos / Quedo pendiente*)
2. ¿Firmas con nombre, apodo, iniciales, emoji o nada?

---

### Tanda 4 — Palabras y frases que **odias** o nunca usarías
> *Lista negra personal.*
1. ¿Palabras que te chirrían ver en un texto tuyo? (ej: *empoderar, resiliencia, sinergia, disruptivo, escalable, performar, holístico, paradigmático*)
2. ¿Frases hechas que evitas? (ej: *al final del día, pensar fuera de la caja, dar el 110%, es lo que hay, mover la aguja, bajar a tierra*)

---

### Tanda 5 — Formalidad según contexto
> *Ajuste de registro.*
Para cada contexto, dime en escala 1–5 (1 = muy informal / 5 = muy formal) y un ejemplo de cómo escribirías "te envío el archivo":
- Amigos / familia cercana
- Familia extensa / conocidos
- Trabajo (compañeros de confianza)
- Trabajo (jefes / clientes formales)
- Escuela / trámites oficiales
- Redes sociales públicas

---

### Tanda 6 — Gustos, referencias y temas recurrentes
> *Tu mundo interno.*
1. ¿Temas que salen solos en tus conversaciones? (ej: café, tacos, series, fútbol, código, perros, política, memes, música, carros, videojuegos)
2. ¿Referencias culturales que usas? (películas, libros, canciones, memes, youtubers, dichos familiares, refranes: *"el que nace pa' tamal...", "a caballo regalado...", "no hay mal que dure..."*)
3. ¿Hay algo que **siempre** menciones o relates? (ej: "como diría mi abuela...", "en mi experiencia...", "la neta...", "te cuento...")

---

## Paso final — Análisis de textos reales
Pide **3 a 5 textos reales** del usuario (WhatsApp, correos, trabajos, posts, notas de voz transcritas). Mínimo 50 palabras cada uno.

**Regla de concordancia:**  
Si lo que el usuario *dijo* en el cuestionario choca con lo que *de verdad escribe* en sus textos, **manda lo que escribe**. El comportamiento real pesa más que la intención declarada.

Analiza:
- Vocabulario real vs. declarado
- Estructura de frases (cortas, largas, fragmentadas)
- Uso real de mayúsculas, signos, emojis
- Ritmo y cadencia
- Muletillas reales vs. declaradas

---

## Salida: plantilla-perfil.md → ~/.claude/la-neta/mi-perfil.md

Llena **plantilla-perfil.md** con toda la info recopilada y guárdala en:
```
~/.claude/la-neta/mi-perfil.md
```

Esa ruta es fija en la carpeta del usuario. La skill crea el directorio `~/.claude/la-neta/` si no existe; sobrescribe el archivo si ya hay uno.

---

## Uso posterior

Escribir textos con el perfil lo hace la skill **escribir-como-yo** de este mismo plugin: se activa sola cuando el usuario pide redactar algo y le pregunta si lo quiere con su estilo. Al terminar el cuestionario, avísale al usuario que ya puede pedir cualquier texto y que se le va a preguntar *"¿Lo escribo como tú o a mi manera?"*.

---

## Notas de implementación

- **Idioma base:** español con variantes regionales (México: norte, frontera, chilango, etc.) pero válido para cualquier hispanohablante.
- **Privacidad:** el perfil **nunca se sube a GitHub** (está en `.gitignore`). Solo lo lee la instancia local de Claude Code. **Cuando la IA lo usa para redactar, el contenido viaja al proveedor como contexto normal**. No pongas datos sensibles.
- **Al cerrar el cuestionario**, describe la privacidad así (no la resumas como "no se sube a ningún lado", porque no es exacto): *"Tu perfil se guarda en tu compu y no se sube a GitHub. Cuando te escriba algo, lo leo como contexto, igual que cualquier mensaje que me mandas."*
- **Actualización:** el usuario puede relanzar la skill cuando quiera para refinar el perfil. La skill detecta si ya existe `~/.claude/la-neta/mi-perfil.md` y pregunta si quiere actualizarlo o partir de cero.

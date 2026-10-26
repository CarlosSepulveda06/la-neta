# la-neta 🇲🇽

Plugin para **Claude Code** que aprende cómo escribes y luego escribe como tú. Te entrevista, lee algunos textos tuyos y arma un perfil con tu forma de hablar. Después, cada vez que le pidas un correo, un mensaje o un trabajo, te pregunta si lo escribe como tú o a su manera.

Está pensado para hispanohablantes, sobre todo mexas: entiende que no escribes igual en el chat con tus compas que en un correo para tu profe.

## Qué trae

| Skill | Qué hace | Estado |
|---|---|---|
| `cuestionario-estilo` | Te hace preguntas cortas por tandas, analiza 3 a 5 textos tuyos y guarda tu perfil en `~/.claude/la-neta/mi-perfil.md` | ✅ |
| `escribir-como-yo` | Se activa sola cuando pides redactar algo. Pregunta *"¿Lo escribo como tú o a mi manera?"* y usa tu perfil según con quién hablas | ✅ |
| `live-dashboard` | Resumen matutino con calendario, correos y pendientes | 🚧 Idea, todavía no funciona |

## Cómo funciona por registro

Tu perfil guarda tus muletillas y modismos, pero no los mete en todos lados:

| Con quién | Qué hace |
|---|---|
| Compas y familia | Escribe con todo tu sabor: tus muletillas, tus saludos, mensajes cortos como en WhatsApp |
| Clientes, conocidos | Cordial, con tus frases suaves ("quedo pendiente", "ahorita") y ortografía corregida |
| Escuela, trámites, jefes | Sin muletillas, con acentos y signos bien puestos, oraciones cortas. Tu voz se nota en cómo explicas, no en el "pues" |

Además, antes de entregarte un texto lo revisa: que no invente datos que no le diste, que no repita la despedida, que pregunte si una hora no dice a.m. o p.m., y que nunca sobrescriba tu archivo original.

## Instalación

Dentro de Claude Code:

```
/plugin marketplace add CarlosSepulveda06/la-neta
/plugin install la-neta@la-neta
```

### Probarlo sin instalar

```
git clone https://github.com/CarlosSepulveda06/la-neta.git
cd la-neta
claude --plugin-dir . --add-dir ~/.claude/la-neta
```

En Windows (CMD) la última línea queda así:

```
claude --plugin-dir . --add-dir "%USERPROFILE%\.claude\la-neta"
```

> **¿Por qué el `--add-dir`?** Tu perfil vive en `~/.claude/la-neta/`, fuera de la carpeta donde arrancas Claude. Sin ese parámetro, Claude te va a pedir permiso para leerlo. Si te lo pide, escoge *"Yes, but ask again next time"*. No le des permiso para leer **cualquier** carpeta fuera del proyecto.

## Uso

**1. Haz tu perfil (una sola vez).** Escríbele a Claude *"hazme el cuestionario de estilo"* o usa `/la-neta:cuestionario-estilo`. Contesta como hablas normalmente. Al final te pide textos tuyos reales: chats, correos, algún trabajo. Entre más variados, mejor sale el perfil.

**2. Pídele cosas normal.** Por ejemplo:

- *"Redáctame un correo para mi profe avisando que entrego tarde la actividad"*
- *"Escríbele a mi compa para ver la carrera el domingo"*
- *"Reescribe este trabajo y guárdalo como archivo nuevo"* + la ruta del archivo

Te va a preguntar si lo escribe como tú y te pide los datos que falten en vez de inventarlos.

**3. Actualiza tu perfil cuando quieras.** Vuelve a correr el cuestionario. Te pregunta si quieres actualizar el perfil o empezar de cero.

## Privacidad

- Tu perfil se guarda en tu compu, en `~/.claude/la-neta/mi-perfil.md`. **No es parte de este repo** y no se sube a ningún lado por el plugin.
- Cuando Claude escribe algo por ti, **lee tu perfil como contexto**, igual que cualquier mensaje que le mandas. O sea, sí viaja al proveedor de la IA mientras lo usa.
- Por eso: **no pongas datos sensibles en tu perfil ni en los textos de ejemplo.** Nada de contraseñas, direcciones, números de cuenta, CURP, RFC o datos de otras personas.

## Estructura

```
.claude-plugin/
  plugin.json           manifiesto del plugin
  marketplace.json      para instalarlo con /plugin
skills/
  cuestionario-estilo/  la entrevista y la plantilla del perfil
  escribir-como-yo/     la que escribe con tu voz
  live-dashboard/       borrador
```

## Licencia

MIT. Úsalo, modifícalo y compártelo. Si lo mejoras, mándame un PR.

Hecho con ganas de que la IA deje de sonar a IA.

# CofundadorIA

Practica la mentoría con un equipo fundador simulado que se equivoca a propósito. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/cofundadoria/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- Simula una reunión con el equipo fundador de una spin-off (2 a 4 personajes ficticios: investigadora cofundadora, socio comercial, inversora ángel y cliente potencial).
- Dos papeles: **mentor del equipo** (guía con preguntas sin decidir ni hacer el trabajo) o **miembro del equipo** (discute con los compañeros y redacta la decisión final).
- Seis decisiones de partida (precio, validación del problema, primer mercado, primera ronda, licencia de la tecnología, reparto del capital) o una decisión libre.
- Antes de empezar, la IA prepara de 2 a 5 errores (dato sin respaldo, supuesto presentado como hecho, cálculo erróneo, riesgo de propiedad intelectual) y **el código decide en qué intervención aparece cada uno**. Los personajes los sueltan con naturalidad y no se revelan hasta el final.
- Durante la sesión, cada mensaje del equipo tiene un botón «Cuestionar».
- Al terminar, un mapa de competencias sin nota (cuatro criterios, cuatro niveles), la tabla de errores sembrados con su resultado, indicadores calculados por código, síntesis e historial de prácticas. Informe en Word y sesión en JSON.
- Ejemplo completo sin clave en los tres idiomas (caso ficticio SensAgro).

## Qué comprueba el código

- Que cada error se sembró de verdad: el personaje debe decirlo y la cita de cómo lo dijo tiene que aparecer literalmente en su mensaje.
- Que un error se detectó: si el participante marcó ese mensaje o si la IA aporta una frase del participante, posterior al error, que aparece literalmente en la conversación. Si la IA lo da por detectado sin esa frase, no cuenta.
- Que cada evidencia del mapa es una frase literal del participante. Un criterio sin evidencia verificada no pasa de «En desarrollo».
- Que los personajes son solo los elegidos, que nadie delata los errores (se quitan sus identificadores) y que el feedback no pone notas ni porcentajes (se eliminan esas frases).

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador. No hace falta servidor.

## Privacidad

El caso, la conversación, los mapas y el historial se guardan solo en el navegador (IndexedDB). En cada llamada salen hacia el proveedor de IA el caso y la conversación, con correos, DNI/NIE y teléfonos enmascarados; antes del primer envío se muestra una muestra de lo que sale y se pide confirmación. No deben escribirse resultados que aún se puedan patentar ni datos confidenciales de una empresa real. El JSON exportado no contiene la clave.

## Límites

- Es una práctica orientativa, no una evaluación certificada: los niveles los propone la IA y el código solo los rebaja cuando falta evidencia.
- La idea procede de un ensayo con 52 estudiantes de emprendimiento (arXiv 2611.02016). Con técnicos de transferencia y emprendimiento no se ha medido su efecto.
- El código comprueba que una frase aparece en la conversación, no que cuestione bien el error: la frase la elige la IA.
- Probada con IA simulada en los tres proveedores; no con una clave real.
- Una sesión completa son unas 12 llamadas cortas a la IA.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche).

Inspirada en Vantage (Google Research) y en el ensayo con estudiantes de emprendimiento de Google Research y NFTE (arXiv 2611.02016): compañeros de IA que discrepan y siembran errores, pero nunca hacen la tarea.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *CofundadorIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).

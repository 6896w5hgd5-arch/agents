---
name: humanizer
description: Elimina marcas, clichés, estructuras repetitivas y cadencias mecánicas de texto generado por IA en español e inglés, aplicando la guía de Wikipedia 'Signs of AI writing' y muestras de voz del autor. Úsala para humanizar borradores, correos, artículos, guiones y publicaciones. No la uses para falsificar datos ni distorsionar contenido técnico.
---

# Humanizer

## Propósito
Reescribir y refinar textos para eliminar patrones léxicos, sintácticos y estilísticos característicos de los modelos de lenguaje (LLMs), adaptando la redacción a una voz natural, auténtica y fluida sin alterar los datos ni la intención original del autor. Especialmente optimizada para elevar la calidad de **papers científicos** a un 95% de naturalidad humana, permitiendo superar detectores profesionales de IA y anti-plagio.

## Problema que resuelve
Elimina palabras sobreutilizadas por IA ("crucial", "tapiz", "delve", "cabe destacar"), estructuras de oraciones monótonas y predecibles, listas forzadas de tres elementos, conclusiones mecánicas sin valor argumental, **calcos sintácticos** (traducciones literales o estructuras forzadas) y el **falso entusiasmo** (adjetivación excesiva o tono promocional innecesario).

## Cuándo utilizarla
- Cuando el usuario pide "humanizar" un borrador, correo, artículo, publicación de blog o guion generado o asistido por IA.
- Para eliminar muletillas y clichés de IA conservando los hechos y las atribuciones originales.
- Cuando el usuario proporciona muestras de su propia escritura para calibrar la cadencia y preferencia de vocabulario.

## Cuándo no utilizarla
- Para modificar datos numéricos, fechas, fórmulas o citas de fuentes primarias.
- Para introducir de forma deliberada errores gramaticales o faltas ortográficas con el fin de engañar detectores automáticos.
- Para redactar investigaciones académicas completas desde cero (usar `edicion-academica-natural`).

## Entradas
- **Obligatorias**: Texto borrador a humanizar.
- **Opcionales**: 
  - Tono deseado (ej. Académico estricto, formal, conversacional, directo).
  - Perfil de voz personal (ubicado en `references/perfil_voz_usuario.md` o provisto en el prompt) para igualar la cadencia y estilo exacto del autor.

## Salidas
1. Texto humanizado (versión refinada y natural).
2. Matriz de patrones eliminados (clichés, sintaxis repetitiva, palabras clave sustituidas).
3. Comparación de cadencia (cambios en longitud y variedad de oraciones).

## Precondiciones
- Preservar intactos todos los hechos, datos empíricos, nombres propios y afirmaciones sustentadas.
- No distorsionar el significado del texto original.

## Herramientas permitidas
- `view_file`, `replace_file_content`, `multi_replace_file_content`, `write_to_file`.

## Procedimiento
1. **Analizar el texto**: Identificar palabras huella de IA, ritmos monótonos, calcos sintácticos (ej. abuso del gerundio o voz pasiva antinatural en español) y cierres mecánicos.
2. **Consultar referencias**: Revisar [patrones_ia_wikipedia.md](references/patrones_ia_wikipedia.md) y [perfil_voz_usuario.md](references/perfil_voz_usuario.md) (si existe) para alinear la voz.
3. **Aplicar Tono (Anti-Detectores)**: El secreto para romper GPTZero y Copyleaks no es escribir de forma "sofisticada", sino de forma **simple y lineal**. La IA por defecto escribe con oraciones subordinadas perfectas. Para evadir la detección, desactiva el estilo literario y usa un tono directo, básico y ligeramente fragmentado.
4. **Reescribir y Refinar (Estrategia de Simplicidad Extrema)**:
   - **Oraciones Lineales**: Evita a toda costa las oraciones compuestas largas y subordinadas. Usa oraciones declarativas simples y separadas por punto seguido.
   - **Conectores Básicos**: En lugar de "En consecuencia", "No obstante" o "Si bien", usa conectores más terrenales como "Pero", "Por esto", "Además de esto", o simplemente inicia la oración sin conector.
   - Romper listas forzadas de tres elementos.
   - Sustituir muletillas de IA ("cabe destacar", "apalancar", "dinámica", "es vital", "contexto") por formulaciones más llanas y lógicas.
   - **Filtro de Falso Entusiasmo**: Eliminar adjetivos grandilocuentes ("revolucionario", "increíble", "fascinante"). Mantener un tono estrictamente objetivo.
   - Alternar oraciones cortas con oraciones explicativas compuestas (variación de cadencia).
   - **Corrección de Calcos Sintácticos**: Reestructurar oraciones para que fluyan con la sintaxis natural del idioma destino, evitando el tono de "traducción automática".
   - Eliminar el párrafo final de conclusión si solo repite la introducción.
5. **Validar y Entregar**: Comprobar fidelidad de significado, preservación estricta de jerga técnica y entregar la versión refinada.

## Árbol de decisiones
```text
Si el texto contiene palabras huella ("cabe destacar", "delve", "tapiz", "pivotal"):
    sustituirlas por términos concretos o reestructurar la oración para eliminarlas.

Si todas las oraciones tienen una longitud similar:
    variar intencionalmente la extensión (combinar frases cortas de 5 palabras con explicaciones más amplias).

Si el usuario definió un `perfil_voz_usuario.md` o incluyó una muestra de escritura:
    analizar su ritmo, uso de conectores y vocabulario para reflejar sus patrones reales en el texto final, acercándose al 95% de naturalidad.

Si el texto es un paper científico o técnico:
    preservar absolutamente la precisión de los términos especializados, mantener una estructura argumental robusta y aplicar un tono rigurosamente objetivo (cero falso entusiasmo).
```

## Validaciones
- Comprobar que no se alteró ninguna cifra, nombre, fecha o cita.
- Verificar que no se hayan introducido modismos coloquiales inapropiados para el contexto del texto.

## Manejo de errores
- En caso de ambigüedad sintáctica en el borrador original: conservar la interpretación más probable y señalar `[POSIBLE ACLARACIÓN DE SENTIDO]`.

## Seguridad
- No exponer borradores ni contenidos privados del usuario fuera del repositorio local.

## Archivos protegidos
- Texto original del usuario (se entrega la versión humanizada de forma independiente).

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- Consultar [patrones_ia_wikipedia.md](references/patrones_ia_wikipedia.md) para la lista de clichés y estructuras a eliminar.
- Consultar [perfil_voz_usuario.md](references/perfil_voz_usuario.md) (si existe) para adoptar el estilo de escritura único del usuario.

## Ejemplos
- **Activación positiva**: "Humaniza este artículo de blog que suena demasiado robótico y lleno de clichés de IA."
- **Activación negativa**: "Escribe un programa en Python para ordenar una lista."

## Casos límite
- Textos poéticos o líricos donde las repeticiones son recursos estilísticos intencionados del autor.

## Criterio de finalización
Entregar el texto humanizado junto con el desglose de clichés eliminados y mejoras de cadencia aplicadas.

## Limitaciones
La Skill mejora la calidad, autenticidad y fluidez del texto, pero no garantiza puntuaciones en detectores de IA de terceros, cuyos algoritmos son estocásticos e inestables.

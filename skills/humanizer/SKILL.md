---
name: humanizer
description: Elimina marcas, clichés, estructuras repetitivas y cadencias mecánicas de texto generado por IA en español e inglés, aplicando la guía de Wikipedia 'Signs of AI writing' y muestras de voz del autor. Úsala para humanizar borradores, correos, artículos, guiones y publicaciones. No la uses para falsificar datos ni distorsionar contenido técnico.
---

# Humanizer

## Propósito
Reescribir y refinar textos para eliminar patrones léxicos, sintácticos y estilísticos característicos de los modelos de lenguaje (LLMs), adaptando la redacción a una voz natural, auténtica y fluida sin alterar los datos ni la intención original del autor.

## Problema que resuelve
Elimina palabras sobreutilizadas por IA ("crucial", "tapiz", "delve", "cabe destacar"), estructuras de oraciones monótonas y predecibles, listas forzadas de tres elementos y conclusiones mecánicas sin valor argumental.

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
- **Opcionales**: Muestras previas de escritura del autor (para calibración de voz), tono deseado (formal, conversacional, profesional).

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
1. **Analizar el texto**: Identificar palabras huella de IA, ritmos monótonos y cierres vacíos.
2. **Consultar la guía de patrones**: Revisar [patrones_ia_wikipedia.md](references/patrones_ia_wikipedia.md).
3. **Calibrar la voz**: Extraer cadencia y preferencias si el usuario incluyó muestras de su escritura.
4. **Reescribir sintácticamente**:
   - Romper listas forzadas de tres elementos.
   - Sustituir muletillas ("cabe destacar", "desempeña un papel fundamental", "sin problemas") por formulaciones directas.
   - Alternar oraciones cortas con oraciones explicativas compuestas.
   - Eliminar el párrafo final de conclusión si solo repite la introducción.
5. **Validar y Entregar**: Comprobar fidelidad de significado y entregar la versión refinada.

## Árbol de decisiones
```text
Si el texto contiene palabras huella ("cabe destacar", "delve", "tapiz", "pivotal"):
    sustituirlas por términos concretos o reestructurar la oración para eliminarlas.

Si todas las oraciones tienen una longitud similar:
    variar intencionalmente la extensión (combinar frases cortas de 5 palabras con explicaciones más amplias).

Si el usuario incluyó una muestra de su propia escritura:
    analizar su ritmo y vocabulario para reflejar sus patrones reales en el texto final.

Si el texto es técnico o científico:
    preservar la precisión de los términos especializados y evitar sustituciones imprecisas.
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

## Ejemplos
- **Activación positiva**: "Humaniza este artículo de blog que suena demasiado robótico y lleno de clichés de IA."
- **Activación negativa**: "Escribe un programa en Python para ordenar una lista."

## Casos límite
- Textos poéticos o líricos donde las repeticiones son recursos estilísticos intencionados del autor.

## Criterio de finalización
Entregar el texto humanizado junto con el desglose de clichés eliminados y mejoras de cadencia aplicadas.

## Limitaciones
La Skill mejora la calidad, autenticidad y fluidez del texto, pero no garantiza puntuaciones en detectores de IA de terceros, cuyos algoritmos son estocásticos e inestables.

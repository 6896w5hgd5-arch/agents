---
name: edicion-academica-natural
description: Edita, audita y organiza borradores académicos propios (ensayos, empíricos, econometría, tesis, revisiones, papers) revisando citas, bibliografía, estructura, evidencia, redundancias y paráfrasis sin inventar fuentes ni alterar el significado. Úsala para mejorar borradores manteniendo la voz del autor. No la uses para redactar investigaciones desde cero ni engañar detectores.
---

# Edición académica natural

## Propósito
Editar, auditar y perfeccionar borradores académicos de cualquier disciplina respetando la voz única del autor, asegurando el rigor argumental, la consistencia entre citas y bibliografía, y la claridad estilística sin inventar fuentes ni alterar el contenido técnico.

## Problema que resuelve
Evita la pérdida de precisión conceptual en la corrección, la homogeneización artificial de la voz del autor (estilo robótico o cliché de IA), la desalineación entre objetivos y conclusiones, y los errores de citación.

## Cuándo utilizarla
- Para la revisión, edición estilística y corrección gramatical de borradores académicos (tesis, artículos, ensayos, informes).
- Para realizar una auditoría integral de manuscrito (coherencia argumental, citas, bibliografía, redundancias y estructura).
- Para elaborar paráfrasis conservadoras o estructurales preservando el significado exacto y las atribuciones de fuentes.

## Cuándo no utilizarla
- Para redactar trabajos de investigación o ensayos desde cero en sustitución del estudiante/investigador.
- Para alterar o inflar de forma engañosa métricas con el fin de eludir detectores automáticos de texto.
- Para inventar o adivinar metadatos bibliográficos, coeficientes econométricos o datos empíricos ausentes.

## Entradas
- **Obligatorias**: Texto borrador del autor.
- **Opcionales**: Muestras de escritura previa del autor, disciplina, género del documento, guía editorial o estilo de citación objetivo.

## Salidas
1. Texto editado (versión completa y fiel).
2. Resumen de cambios relevantes (claridad, lógica, tono, precisión).
3. Auditoría de citas y auditoría de bibliografía (tabla de correspondencia, hallazgos y prioridades).
4. Diagnóstico de estructura, redundancias detectadas y paráfrasis propuestas.
5. Puntos a confirmar por el autor y 3 aprendizajes prácticos para futuros borradores.

## Precondiciones
- Disponer del borrador del autor y, cuando exista, consultar `references/perfil_autor.md`.
- Garantizar que los datos, fechas, nombres, fórmulas y citas se mantengan intactos salvo error gramatical explícito.

## Herramientas permitidas
- `view_file`, `replace_file_content`, `multi_replace_file_content`, `write_to_file`.

## Procedimiento
1. **Comprender la intención**: Leer el borrador sin modificar datos ni fuentes.
2. **Clasificar el género y diseño**: Consultar [estructuras_investigacion.md](references/estructuras_investigacion.md).
3. **Auditar coherencia argumental**: Mapear problema -> objetivos -> método -> resultados -> conclusiones.
4. **Auditar citas y bibliografía**: Cruzar referencias con [auditoria_bibliografica.md](references/auditoria_bibliografica.md).
5. **Detectar redundancias y corregir redacción**: Eliminar muletillas y cliché de IA sin alterar el sentido.
6. **Formular recomendaciones y entregar**: Entregar la versión editada y los diagnósticos.

## Árbol de decisiones
```text
Si el usuario solicita optimizar el texto para superar un detector de IA:
    rehusar la manipulación engañosa.
    volver a criterios verificables: claridad, rigor, fuentes y voz del autor.

Si una cita respalda solo parcialmente una oración:
    dividir la oración o restringir la afirmación para reflejar exactamente el alcance de la fuente.

Si falta un dato bibliográfico clave:
    marcar como '[REQUIERE VERIFICACIÓN DE FUENTE]' o '[REQUIERE ACLARACIÓN DEL AUTOR]'.
    NO completar de memoria.
```

## Validaciones
- Comprobar que no se inventaron datos, coeficientes ni citas bibliográficas.
- Comprobar que cada redundancia eliminada no cumplía una función argumental de transición o énfasis necesario.

## Manejo de errores
- Ante textos altamente fragmentados o ambiguos: marcar `[POSIBLE CAMBIO DE SIGNIFICADO]` antes de proponer cualquier reorganización profunda.

## Seguridad
- No exponer borradores o trabajos académicos no publicados fuera del entorno local del usuario.

## Archivos protegidos
- Borradores originales del autor (se entrega versión editada sin sobrescribir el fuente).

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- Consultar [estructuras_investigacion.md](references/estructuras_investigacion.md) para patrones por disciplina.
- Consultar [auditoria_bibliografica.md](references/auditoria_bibliografica.md) para verificación de citaciones.
- Consultar `references/perfil_autor.md` si está disponible.

## Ejemplos
- **Activación positiva**: "Revisa este artículo empírico de economía: audita la coherencia entre método y conclusiones y corrige la redacción."
- **Activación negativa**: "Escribe mi tesis de maestría sobre literatura hispanoamericana."

## Casos límite
- Textos académicos traducidos de otros idiomas con calcos sintácticos complejos.
- Manuscritos multiautor con notables discrepancias de tono entre secciones.

## Criterio de finalización
Entregar el borrador editado junto con la auditoría de citas/bibliografía, la tabla de redundancias y las observaciones para el autor.

## Limitaciones
La Skill mejora el rigor formal, estructural y lingüístico del texto, pero no valida la corrección teórica ni los cómputos matemáticos del trabajo del usuario.


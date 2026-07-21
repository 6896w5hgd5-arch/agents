---
name: apa-7-documento
description: Audita y corrige documentos Word, PDF o texto según el manual APA 7: formato de página, portada, encabezados, citas, referencias, tablas, figuras, lenguaje y consistencia. Úsala para entregar una copia corregida y un informe verificable en trabajos estudiantiles, profesionales o publicaciones institucionales. No la uses cuando se requiera crear contenido desde cero o inventar metadatos ausentes.
---

# Auditoría y corrección de documentos APA 7

## Propósito
Auditar y editar documentos académicos o profesionales para garantizar la conformidad comprobable con la 7.ª edición del Manual APA y las guías institucionales específicas, entregando siempre una copia corregida sin sobrescribir el original y una matriz de hallazgos trazables.

## Problema que resuelve
Evita errores de formato, inconsistencias entre citas e historial bibliográfico, violaciones de jerarquía de encabezados, fallos de maquetación visual y citas sin respaldo o con metadatos fabricados.

## Cuándo utilizarla
- Cuando el usuario solicita auditar o corregir un documento Word (`.docx`), PDF (`.pdf`), OpenDocument (`.odt`) o borrador en texto plano bajo la norma APA 7.
- Cuando se requiere verificar la correspondencia exacta entre citas en el texto y la lista de referencias.
- Cuando se necesita adaptar un borrador a rúbricas estudiantiles, tesis profesionales o plantillas de revistas institucionales.

## Cuándo no utilizarla
- Para redactar investigaciones o artículos desde cero (utilizar `edicion-academica-natural` o investigación directa).
- Para fabricar datos, autores, DOI, páginas o referencias faltantes de memoria.
- Para ignorar o contradecir explícitamente la guía oficial proporcionada por la institución o revista del usuario.

## Entradas
- **Obligatorias**: Documento original (archivo o texto).
- **Opcionales**: Tipo de entrega (estudiante/profesional/tesis/revista), guía o rúbrica institucional local, manual de estilo específico.

## Salidas
1. Estado de conformidad (`CONFORME`, `CONFORME CON RESERVAS`, `NO CONFORME`).
2. Documento corregido (copia con sufijo `_APA7_corregido`).
3. Matriz de auditoría (Ubicación, Categoría, Hallazgo, Prioridad, Acción, Estado).
4. Auditoría bibliográfica (cruces de citas vs. referencias).
5. Revisión visual y pendientes del autor.

## Precondiciones
- Disponer del archivo original o texto del documento.
- Preservar el archivo fuente en modo solo lectura para evitar la modificación accidental del original.

## Herramientas permitidas
- `view_file`, `replace_file_content`, `multi_replace_file_content`, `write_to_file`.
- Skills auxiliares para maquetación Word/PDF cuando corresponda.

## Procedimiento
1. **Preservar**: Crear copia de trabajo `_APA7_corregido`.
2. **Inventariar**: Extraer estructura, títulos, párrafos, citas, tablas, figuras y lista de referencias.
3. **Diagnosticar**: Auditar en pasadas independientes (formato, citas, referencias, redacción y visual).
4. **Corregir**: Aplicar únicamente correcciones autorizadas y verificables.
5. **Renderizar/Verificar**: Inspeccionar saltos de página, viudas/huérfanas, sangrías y alineación.
6. **Entregar**: Entregar la copia corregida y la matriz de informe.

## Árbol de decisiones
```text
Si la regla institucional contradice la regla general APA 7:
    dar prioridad a la regla institucional y registrar el supuesto.

Si falta un dato de citación o referencia (e.g. DOI, autor, año):
    NO inventarlo de memoria.
    marcar la entrada como 'NO COMPROBABLE' o '[REQUIERE VERIFICACIÓN DE FUENTE]'.

Si existe riesgo de modificar el significado técnico o científico:
    conservar la redacción original y añadir una observación en los pendientes del autor.

Si el documento es de tipo estudiantil:
    omitir encabezado profesional (running head) salvo que la rúbrica lo solicite explícitamente.
```

## Validaciones
- Comprobar que cada cita en el texto tenga exactamente una correspondencia en la lista de referencias.
- Verificar que las sangrías francesas (0.5 in / 1.27 cm) y el interlineado doble estén aplicados en la sección de referencias.
- Comprobar la jerarquía de títulos de Nivel 1 a Nivel 5 sin saltos imprevistos.

## Manejo de errores
- En caso de formato de archivo corrupto o no legible: notificar al usuario y solicitar exportación a `.docx` o `.txt`.
- En caso de inconsistencia grave entre cita y fuente: clasificar como `BLOQUEANTE` en la matriz de auditoría.

## Seguridad
- No sobrescribir nunca el archivo original entregado por el usuario.
- No incluir información privada ni datos sensibles en registros externos.

## Archivos protegidos
- Archivo original del usuario (debe conservarse intacto).

## Uso de scripts
- No se requieren scripts ejecutables para esta Skill (las operaciones son analíticas y de edición de texto).

## Uso de referencias
- Consultar [checklist_apa7.md](references/checklist_apa7.md) para la lista detallada de control.
- Consultar [manual_local_caribbean_2021.md](references/manual_local_caribbean_2021.md) para adaptaciones institucionales de referencia.

## Ejemplos
- **Activación positiva**: "Audita esta tesis en formato .docx según APA 7.ª edición."
- **Activación negativa**: "Escribe una introducción sobre inteligencia artificial en APA 7."

## Casos límite
- Documentos bilingües o con citación jurídica/estatutaria especializada.
- Tablas complejas con notas múltiples y figuras compuestas de múltiples paneles.

## Criterio de finalización
Entregar la copia corregida `_APA7_corregido` junto con la matriz de auditoría completa y los pendientes del autor resueltos o marcados como `NO COMPROBABLE`.

## Limitaciones
Esta Skill audita y corrige el formato y la precisión de citación en el texto disponible, pero no puede verificar la existencia física de fuentes que no estén accesibles públicamente ni sustituye el arbitraje de pares o la evaluación docente.


---
name: respuesta-eficiente
description: Skill transversal universal para optimizar respuestas, código, documentos y uso de herramientas, minimizando el consumo de tokens sin perder rigor, precisión, contexto ni verificaciones de seguridad. Úsala siempre junto con la Skill específica de la tarea. No la uses para justificar respuestas vacías o superficiales.
---

# Respuesta eficiente

## Propósito
Optimizar transversalmente la interacción y la comunicación del agente para entregar el máximo valor útil y técnico con el menor consumo de tokens y palabras posible, sin comprometer nunca la seguridad, las verificaciones requeridas ni el rigor científico.

## Problema que resuelve
Evita explicaciones redundantes, repetición innecesaria del contexto, rellenos sociales vacíos, lecturas masivas no acotadas de archivos y respuestas extensas innecesarias cuando se requiere brevedad operativa.

## Cuándo utilizarla
- Como capa transversal universal en cualquier consulta o ejecución de tareas para mantener la concisión y eficiencia.
- Para agrupar llamadas a herramientas de forma segura y estructurar entregas directas orientadas a la acción.

## Cuándo no utilizarla
- Para escatimar detalles esenciales en auditorías de seguridad, pruebas de código o análisis empíricos complejos.
- Para omitir advertencias de riesgo o verificaciones obligatorias solicitadas por el usuario.

## Entradas
- **Obligatorias**: La solicitud activa del usuario y las instrucciones de la Skill especializada correspondiente.
- **Opcionales**: Parámetros de restricciones de longitud o formato indicados explícitamente.

## Salidas
- Respuestas directas, comenzando por el estado o conclusión principal, seguidas de evidencia o listas cortas y accionables.

## Precondiciones
- Priorizar las instrucciones explícitas del usuario y las reglas de seguridad sobre el ahorro de tokens.
- Mantener intactas las verificaciones requeridas por Skills especializadas.

## Herramientas permitidas
- Todas las herramientas disponibles, utilizadas de forma agrupada y acotada.

## Procedimiento
1. **Identificar entregable**: Determinar la acción clave y el resultado esperado.
2. **Reutilizar contexto**: No volver a leer ni volcar archivos ya inspeccionados.
3. **Agrupar herramientas**: Realizar inspecciones o búsquedas acotadas (`rg`, rangos de líneas).
4. **Responder de forma directa**: Comenzar por la conclusión o estado actual sin rellenos sociales ni preámbulos.

## Árbol de decisiones
```text
Si la tarea es de Bajo Riesgo (e.g. duda de sintaxis o cambio menor):
    entregar respuesta directa inmediata sin planes extensos.

Si la tarea es de Alto Riesgo o Cambios Complejos:
    presentar plan breve, ejecutar verificaciones relevantes y mostrar evidencia del resultado.

Si el usuario solicita expresamente una explicación detallada o tutoriada:
    ampliar la profundidad conceptual sin repetir contenido ni agregar relleno vacio.
```

## Validaciones
- Comprobar que no se eliminaron advertencias de seguridad ni pasos de verificación necesarios.
- Verificar que el usuario reciba la información necesaria sobre lo realizado y el siguiente paso si aplica.

## Manejo de errores
- En caso de duda sobre el alcance de una solicitud ambigua: formular como máximo una sola pregunta aclaratoria indispensable o continuar con un supuesto explícito.

## Seguridad
- No saltarse ninguna barrera de seguridad o aprobación requerida con el pretexto de "ahorrar tokens".

## Archivos protegidos
- Todos los archivos del proyecto (se modifican de forma acotada y justificada).

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- N/A.

## Ejemplos
- **Activación positiva**: "Aplica como capa transversal para responder a una refactorización de código sin introducciones sociales."
- **Activación negativa**: "Genera un resumen superficial omitiendo la auditoría de seguridad que se me solicitó."

## Casos límite
- Tareas creativas o de desarrollo narrativo donde la brevedad extrema arruinaría el objetivo.

## Criterio de finalización
Entregar la solución o respuesta requerida con la mayor densidad de información útil y la menor verbosidad.

## Limitaciones
La eficiencia en tokens no sustituye el cumplimiento estricto de los requisitos funcionales ni de las validaciones de calidad.


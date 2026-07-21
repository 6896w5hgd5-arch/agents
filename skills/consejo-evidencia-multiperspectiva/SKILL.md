---
name: consejo-evidencia-multiperspectiva
description: Analiza decisiones, diseños, planes y afirmaciones complejas desde seis perspectivas independientes (Contrarian, First Principles, Expansionist, Outsider, Executor y Auditor de Evidencia Científica). Úsala cuando el usuario pida un consejo, pressure-test, revisión multiperspectiva o validación de una decisión técnica, académica o de producto. No la uses para preguntas triviales, transcripciones o datos factuales simples.
---

# Consejo de seis perspectivas

## Propósito
Analizar decisiones complejas con incertidumbre o costes elevados mediante seis lentes analíticas independientes para identificar riesgos, puntos ciegos, supuestos débiles y la veracidad empírica de las afirmaciones antes de ejecutar acciones.

## Problema que resuelve
Evita el sesgo de confirmación, la visión de túnel en decisiones de alto impacto, la aceptación acrítica de supuestos no probados y la ejecución de planes con fallos conceptuales o de evidencia.

## Cuándo utilizarla
- Cuando el usuario solicita un consejo, "pressure-test", revisión multiperspectiva o evaluación de riesgo para una decisión técnica, de producto o académica.
- Cuando existen múltiples alternativas con compensaciones (trade-offs) difíciles de cuantificar.
- Antes de realizar una inversión significativa de tiempo, recursos o cambios arquitectónicos irreversibles.

## Cuándo no utilizarla
- Para consultas triviales o factuales directas (e.g. "¿cuál es la sintaxis de X función?").
- Para transcripciones de audio, resúmenes simples de texto o correcciones gramaticales.
- Para tareas automatizadas deterministas donde no exista incertidumbre.

## Entradas
- **Obligatorias**: Planteamiento del problema, decisión o plan a evaluar.
- **Opcionales**: Alternativas consideradas, restricciones conocidas, contexto de negocio/técnico y fuentes bibliográficas.

## Salidas
Un informe estructurado con 8 secciones obligatorias:
1. Pregunta delimitada.
2. Hechos verificados.
3. Coincidencias del consejo.
4. Desacuerdos y riesgos.
5. Auditoría de evidencia.
6. Recomendación razonada.
7. Primer paso concreto.
8. Qué falta confirmar.

## Precondiciones
- Delimitar con precisión el alcance y las restricciones del problema a evaluar.
- No asumir consensos automáticos entre perspectivas sin análisis empírico.

## Herramientas permitidas
- `view_file`, `search_web`, `read_url_content`.

## Procedimiento
1. **Delimitar la decisión**: Identificar objetivo, restricciones y coste de equivocarse.
2. **Reunir contexto mínimo**: Consultar únicamente archivos o datos explícitamente indicados.
3. **Evaluar 6 perspectivas**:
   - **Contrarian**: Fallos fatales y supuestos débiles.
   - **First Principles**: Reconstrucción desde primeros principios y objetivos reales.
   - **Expansionist**: Oportunidades y alternativas de mayor alcance.
   - **Outsider**: Visión externa sin sesgo de contexto interno.
   - **Executor**: Pasos ejecutables, costes, dependencias y primer experimento.
   - **Auditor de evidencia científica**: Verificación de fuentes primarias, cifras, fechas, metodología y causalidad.
4. **Contrastar**: Sintetizar coincidencias, desacuerdos y supuestos compartidos.
5. **Entregar**: Producir el informe final estructurado.

## Árbol de decisiones
```text
Si la decisión tiene baja incertidumbre y bajo impacto:
    recomendar la respuesta directa y omitir el consejo complejo.

Si la evidencia de una afirmación clave no puede verificarse:
    marcar como 'NO CONFIRMADA' o 'REQUIERE FUENTE'.
    NO completar ni asumir veracidad de memoria.

Si existe un desacuerdo crítico entre el Executor y el Contrarian:
    proponer un experimento piloto pequeño y reversible antes de la implementación total.
```

## Validaciones
- Verificar que el informe contenga las 6 perspectivas analizadas explícitamente.
- Comprobar que toda afirmación científica o empírica incluya su etiqueta de estado (`VERIFICADA`, `PARCIAL`, `REQUIERE FUENTE`, `NO CONFIRMADA`, `POSIBLE SOBREINTERPRETACIÓN`).

## Manejo de errores
- Ante la falta de información crucial del problema: formular como máximo una sola pregunta aclaratoria indispensable.
- Ante fuentes contradictorias: registrar las discrepancias y mantener el estado como no concluido.

## Seguridad
- No ejecutar acciones destructivas, instalaciones, commits ni deploys como consecuencia del consejo.
- No solicitar ni leer credenciales, datos privados ni secretos del entorno.

## Archivos protegidos
- Archivos de configuración de producción e información confidencial del usuario.

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- Utilizar fuentes primarias y literatura científica indexada cuando sea aplicable.

## Ejemplos
- **Activación positiva**: "Evalúa desde múltiples perspectivas si debemos migrar nuestra base de datos de PostgreSQL a DynamoDB."
- **Activación negativa**: "¿Cómo se escribe un bucle for en Python?"

## Casos límite
- Decisiones con restricciones éticas, legales o regulatorias estrictas.
- Escenarios con ausencia total de datos históricos o empíricos.

## Criterio de finalización
Entregar las 8 secciones obligatorias del informe con las afirmaciones empíricas debidamente auditadas y clasificadas.

## Limitaciones
El consejo proporciona análisis analítico y metodológico pero no sustituye decisiones de gobernanza legal, comités de auditoría médica o aprobaciones de seguridad institucional.


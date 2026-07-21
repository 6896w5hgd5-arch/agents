---
name: direccion-visual-universal
description: Diseña sistemas visuales coherentes y adaptables para videojuegos, interfaces web, aplicaciones de escritorio, documentos, presentaciones, gráficos académicos, branding y prompts de imágenes. Úsala cuando se requiera definir estéticas, analizar referencias visuales, crear guías de estilo o tokens de diseño. No la uses para editar archivos CSS/código directamente sin un diseño previo.
---

# Dirección visual universal

## Propósito
Diseñar sistemas visuales coherentes, adaptables y profesionales convirtiendo intenciones estéticas o referencias en reglas reutilizables (tokens de color, tipografía, composición, escala, movimiento y estados) para cualquier medio o soporte.

## Problema que resuelve
Evita la mezcla caótica de estilos ("style soup"), la falta de jerarquía de lectura, contrastes inaccesibles (violaciones WCAG), tipografías incoherentes y la copia directa de obras protegidas.

## Cuándo utilizarla
- Cuando el usuario pide definir la dirección artística o visual de un proyecto (videojuego, web, app, marca, documento o presentación).
- Para estructurar sistemas de diseño, paletas de colores accesibles, tipografías y reglas de composición.
- Para formular prompts de generación visual detallados sin ambigüedad estética.

## Cuándo no utilizarla
- Para realizar retoques fotográficos puntuales o generar imágenes directamente si no se solicita una dirección estética previa (usar herramientas de generación directa).
- Para alterar contenido de datos empíricos o gráficos académicos distorsionando la verdad científica.

## Entradas
- **Obligatorias**: Encargo o intención estética, medio de destino (juegos/web/doc/marca/etc.).
- **Opcionales**: Referencias visuales, restricciones técnicas, plataforma objetivo y activos existentes.

## Salidas
Un documento de sistema visual estructurado en 6 secciones:
1. Intención y supuestos.
2. Dirección elegida.
3. Sistema visual (Tokens de color, tipografía, grid, sombras, bordes, estados).
4. Aplicación al medio solicitado.
5. Validación y pruebas (legibilidad, contraste, responsive).
6. Siguientes decisiones.

## Precondiciones
- Respetar la función principal del producto sobre la decoración superficial.
- No clonar la identidad o copyright de artistas o marcas protegidas.

## Herramientas permitidas
- `view_file`, `generate_image`.

## Procedimiento
1. **Delimitar el encargo**: Identificar objetivo, audiencia, medio, plataforma y restricciones.
2. **Analizar referencias**: Separar composición, jerarquía, paleta, textura y movimiento.
3. **Elegir dirección**: Seleccionar un concepto principal y máximo un acento secundario.
4. **Construir el sistema**: Entregar tokens concretos (color HSL/HEX por función, tipografía, grid, bordes, movimiento).
5. **Adaptar al medio**:
   - **Videojuego**: HUD, siluetas, legibilidad a resolución objetivo.
   - **Web/Escritorio**: Responsive, contraste WCAG AA/AAA, estados de foco y error.
   - **Documentos/Diapositivas**: Jerarquía de páginas, estilos editables.
   - **Investigación**: Claridad empírica sin adorno superfluo.
6. **Validar y Entregar**: Probar legibilidad y entregar el informe del sistema visual.

## Árbol de decisiones
```text
Si el medio es un videojuego:
    priorizar siluetas, legibilidad a la resolución objetivo y separación lógica/presentación.

Si el medio es una interfaz web o app:
    garantizar contraste mínimo WCAG AA (4.5:1) para texto normal y tokens de estado (error, carga, éxito).

Si faltan datos de referencias visuales:
    consultar [catalogo_estilos.md](references/catalogo_estilos.md) para comparar alternativas y formular supuestos explícitos.
```

## Validaciones
- Comprobar que los tokens de color especifiquen función (fondo, superficie, texto, acción, error).
- Verificar que las tipografías sugeridas cuenten con alternativas web/sistema seguras.

## Manejo de errores
- Ante referencias conflictivas ("queremos algo minimalista pero con muchos adornos recargados"): señalar la contradicción y proponer una solución jerarquizada.

## Seguridad
- No descargar ni instalar paquetes de tipografías o software de terceros sin autorización explícita y verificación de licencias.

## Archivos protegidos
- Assets y logos originales del usuario.

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- Consultar [catalogo_estilos.md](references/catalogo_estilos.md) para comparar familias y movimientos estéticos.

## Ejemplos
- **Activación positiva**: "Diseña una dirección visual dark-mode moderna para una aplicación web de finanzas."
- **Activación negativa**: "Corrige este error de sintaxis en CSS."

## Casos límite
- Diseño de interfaces para usuarios con baja visión o daltonismo extremo.
- Maquetación para impresión de alta resolución en formatos no estándar.

## Criterio de finalización
Entregar la propuesta del sistema visual con todos sus tokens y las 6 secciones requeridas de salida.

## Limitaciones
Esta Skill define directrices, especificaciones visuales y tokens de diseño, pero requiere la implementación en código CSS/UI por parte del desarrollador o del agente en la fase de construcción.
. **Siguientes decisiones.** Solo las preguntas que cambien materialmente el resultado.

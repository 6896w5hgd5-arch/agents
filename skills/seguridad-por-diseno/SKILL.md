---
name: seguridad-por-diseno
description: Evalúa riesgos técnicos, de privacidad, licencias, propiedad intelectual, seguridad de agentes de IA y cumplimiento antes de programar, instalar, publicar o compartir datos. Úsala para auditorías preventivas en software, juegos, web, repositorios o automatizaciones. No la uses para ejecutar pentesting intrusivo no autorizado ni emitir dictámenes legales.
---

# Seguridad por diseño

## Propósito
Evaluar preventivamente los riesgos técnicos, de privacidad, licencias, propiedad intelectual y seguridad de agentes de IA antes de realizar cambios de código, instalaciones, publicaciones o despliegues, convirtiendo intenciones en decisiones trazables (`APROBAR`, `APROBAR CON CONTROLES`, `POSPONER`, `NO HACER`).

## Problema que resuelve
Evita la filtración accidental de secretos (`.env`, tokens, credenciales) en repositorios públicos, la infracción de licencias de software/assets, vulnerabilidades de inyección o traversal, la ejecución descontrolada de agentes de IA y el borrado irreversible de datos.

## Cuándo utilizarla
- Antes de publicar repositorios, instalar paquetes de terceros, integrar APIs externas o modificar permisos/configuraciones de producción.
- Para realizar auditorías de seguridad por diseño en proyectos web, escritorio, juegos o automatizaciones de agentes.
- Para evaluar la licitud y los riesgos de privacidad/propiedad intelectual de activos y conjuntos de datos.

## Cuándo no utilizarla
- Para ejecutar pruebas de penetración intrusivas o exploits contra sistemas de terceros sin autorización explícita.
- Como sustituto formal de un dictamen legal de abogados o una certificación de auditoría oficial de cumplimiento.

## Entradas
- **Obligatorias**: Descripción del cambio, arquitectura, dependencias o activos a evaluar.
- **Opcionales**: Entorno de ejecución (dev/staging/prod), clasificación de datos y licencias de dependencias.

## Salidas
Un informe de seguridad con 8 secciones obligatorias:
1. Decisión y alcance (`APROBAR` / `APROBAR CON CONTROLES` / `POSPONER` / `NO HACER`).
2. Clasificación de activos y datos (`PÚBLICA`, `INTERNA`, `CONFIDENCIAL`, `SECRETA`).
3. Modelado de amenazas (actor, activo, vector, impacto, control).
4. Riesgos legales y de licencia.
5. Controles mínimos requeridos.
6. Pruebas de verificación (positivas y negativas).
7. Primer paso reversible.
8. Registro de decisiones y supuestos.

## Precondiciones
- Mantener secretos, API keys y tokens fuera del código fuente, prompts, capturas y logs.
- Preservar copias de respaldo antes de sugerir cualquier cambio de configuración.

## Herramientas permitidas
- `view_file`, `grep_search`, `list_dir`.

## Procedimiento
1. **Definir el cambio**: Identificar activos, usuarios, entornos y costes de falla.
2. **Clasificar datos**: Etiquetar datos por confidencialidad y minimizar retención.
3. **Modelar amenazas**: Analizar inyección, prompt injection, bypass de autenticación y fugas.
4. **Revisar licencias**: Verificar licencias de código y activos (MIT, Apache, GPL, CC, etc.).
5. **Establecer controles mínimos**: Menor privilegio, validación de entradas, saneamiento de salidas.
6. **Diseñar pruebas y decidir**: Definir caso de prueba y emitir el veredicto final.

## Árbol de decisiones
```text
Si el cambio contiene secretos o credenciales expuestas en texto plano:
    emitir veredicto 'NO HACER' inmediatamente.
    exigir migración de llaves a variables de entorno (.env sin comitear).

Si la dependencia utiliza una licencia incompatible o ambigua:
    emitir veredicto 'POSPONER' y marcar 'REQUIERE REVISIÓN PROFESIONAL'.

Si se propone una operación destructiva o modificación fuera del alcance:
    detener la ejecución y solicitar aprobación explícita del usuario.
```

## Validaciones
- Comprobar que ningún archivo `.env` con secretos reales se encuentre staged en Git.
- Verificar que las validaciones de entrada prevengan traversal de directorios y ejecución arbitraria de comandos.

## Manejo de errores
- En caso de detectar vulnerabilidades de prioridad `BLOQUEANTE`: detener el flujo de trabajo y notificar de inmediato al usuario antes de modificar archivos.

## Seguridad
- Prohibir la ejecución de comandos destructivos (`rm -rf`, `DROP DATABASE`, etc.) sin confirmación previa y directa.

## Archivos protegidos
- Archivos `.env`, claves privadas, certificados SSL, llaves SSH y datos confidenciales.

## Uso de scripts
- No requiere scripts ejecutables.

## Uso de referencias
- Consultar [guia_controles.md](references/guia_controles.md) para la matriz por tipo de proyecto y referencias de buenas prácticas.

## Ejemplos
- **Activación positiva**: "Audita la seguridad de esta API Node.js antes de desplegarla en producción."
- **Activación negativa**: "Ejecuta un ataque de denegación de servicio contra el servidor X."

## Casos límite
- Sistemas distribuidos multinube con fronteras de cumplimiento regulatorio cruzadas (GDPR, HIPAA, SOC2).

## Criterio de finalización
Entregar el informe de seguridad con las 8 secciones obligatorias y el veredicto trazable emitido.

## Limitaciones
La Skill evalúa y propone controles preventivos, pero no garantiza la ausencia absoluta de vulnerabilidades no descubiertas o de día cero.


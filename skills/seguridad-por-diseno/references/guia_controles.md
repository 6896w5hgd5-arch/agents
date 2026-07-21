# Guía de controles y fuentes

## Matriz rápida

| Contexto | Riesgos prioritarios | Controles iniciales |
|---|---|---|
| Windows/Git | secretos, permisos, ejecutables no confiables, pérdida de datos | `.gitignore`, revisión de cambios, copias, fuentes oficiales, menor privilegio |
| Python | dependencia comprometida, ejecución arbitraria, datos sensibles | entorno aislado, versiones fijadas, revisión de paquetes, pruebas y auditoría de dependencias |
| Web/API | autenticación, autorización, inyección, XSS, CSRF, exposición de datos | validación, sesiones seguras, límites, logs redacted, pruebas negativas |
| Escritorio/juego | archivos manipulados, assets sin licencia, mods maliciosos, rutas inseguras | rutas permitidas, separación de datos/lógica, assets propios y pruebas de carga |
| NicoAgent/IA | prompt injection, herramientas excesivas, fuga de secretos, código no revisado | sandbox, allowlist, aprobación humana, salida no confiable y auditoría |
| Paper/investigación | plagio, datos personales, fuentes inventadas, falta de trazabilidad | citas verificadas, licencias, datos anonimizados, registro de IA y reproducibilidad |

## Puerta de decisión

- **APROBAR:** riesgo bajo, autorización clara, controles y pruebas suficientes.
- **APROBAR CON CONTROLES:** puede avanzar solo con condiciones explícitas y reversibles.
- **POSPONER:** falta evidencia, permiso, fuente, licencia, prueba o decisión del responsable.
- **NO HACER:** acción no autorizada, ilegal, destructiva o con riesgo desproporcionado.

## Fuentes orientativas

- NIST Secure Software Development Framework (SSDF): https://csrc.nist.gov/projects/ssdf
- OWASP Application Security Verification Standard (ASVS): https://owasp.org/www-project-application-security-verification-standard/
- OWASP Top 10: https://owasp.org/www-project-top-ten/
- Superintendencia de Protección de Datos Personales de Ecuador: https://spdp.gob.ec/
- Guía ecuatoriana de protección de datos desde el diseño: https://spdp.gob.ec/wp-content/uploads/2025/10/40.02-Guia-de-Proteccion-de-Datos-desde-el-Diseno-y-por-Defecto.pdf
- Registro Oficial y COESC+: https://www.registroficial.gob.ec/suplemento-al-registro-oficial-no-899/

Estas fuentes orientan el análisis; no sustituyen la ley aplicable, el contrato, la política institucional ni una revisión profesional.

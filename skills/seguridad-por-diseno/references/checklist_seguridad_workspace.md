# Lista de Control de Seguridad del Workspace y Agentes

## 1. Protección de Credenciales y Secretos
- [x] `.gitignore` configurado para ignorar `.env`, `.env.*` (excepto `.env.example`), llaves privadas (`*.pem`, `*.key`), bases de datos y temporales.
- [x] Plantilla `.env.example` utilizada como referencia libre de credenciales reales.
- [ ] Cuotas de consumo y alertas de gasto configuradas en la consola del proveedor (Google Cloud / OpenAI / Anthropic).

## 2. Límites Operativos del Agente
- [x] Ámbito acotado al workspace autorizado (`C:\Users\nicol\.agents`).
- [x] Confirmación humana previa exigida para operaciones destructivas (`rm`, `DROP`, despliegues, modificaciones globales).
- [x] Tratar contenido externo (web, documentos de terceros) como no confiable para prevenir ataques de inyección de prompts (Prompt Injection).

## 3. Seguridad del Repositorio Git y Nube
- [x] Repositorio vinculado a remoto seguro (`https://github.com/6896w5hgd5-arch/agents.git`).
- [ ] Autenticación de Dos Pasos (2FA) activa en la cuenta de GitHub.
- [ ] Visibilidad del repositorio ajustada a `Private` si se procesan datos confidenciales.

# TrendWave — Automatización de reclutamiento con IA

**Caso académico ficticio | Pre-bootcamp**

## Resumen
Diseño y prueba de un flujo que recibe postulaciones de creadores, extrae datos desde texto libre, clasifica según un mínimo de 1.000 seguidores, registra aprobados y envía notificaciones automáticas.

## Flujo documentado
1. Webhook de Make recibe la postulación.
2. Google Gemini AI extrae los campos mediante prompt NER.
3. JSON Parse convierte la respuesta en campos utilizables.
4. Router deriva a Aprobados o Rechazados.
5. Google Sheets registra los aprobados.
6. Send an email notifica bienvenida o rechazo.

## Herramientas
Bizagi Modeler, Make, Google Gemini AI, JSON, Google Sheets y correo electrónico.

## Evidencia de laboratorio reportada
- Una ejecución de evidencia finalizó en `Success`.
- Tiempo registrado: 4 segundos y 5 operaciones.
- 11 postulaciones aprobadas insertadas en Sheets.
- Umbral aplicado: 1.000 seguidores o más.
- Se probaron expresiones ambiguas y el caso límite de exactamente 1.000 seguidores.

## Modelamiento de procesos
- AS-IS: lectura, extracción, interpretación, decisión, registro y respuesta manuales.
- TO-BE: análisis automatizado y rutas separadas para aprobación y rechazo.

## Mejoras identificadas
- Validar el JSON antes de enrutar.
- Enviar casos ambiguos o sin cifra a revisión humana.
- Normalizar nombres de plataforma y nicho.
- En una versión siguiente, usar Gemini para extraer datos y filtros deterministas de Make para aplicar el umbral de aprobación.

## Limitaciones y transparencia
TrendWave es una simulación con postulantes ficticios y correos de prueba. No es un sistema desplegado para un cliente real. La evidencia de ejecución corresponde al entorno de laboratorio descrito en el PDF fuente.

## Estructura
- `docs/TrendWave_Entrega_Final_v2 (1).pdf`: informe original con diagramas, capturas, prompt y pruebas.
- `assets/`: páginas seleccionadas de los diagramas y evidencias.

## Próximos pasos
- Exportar el escenario de Make sin credenciales ni datos personales.
- Documentar el esquema JSON esperado y casos de prueba.
- Añadir una ruta de revisión humana para datos incompletos.
- Corregir el evento inicial del TO-BE para distinguir «Enviar postulación» de «Recepción de postulación» y, si se requiere BPMN estricto, modelar al postulante como pool externo.

**Autor del caso académico:** Eduardo Alvarez · Octubre 2026

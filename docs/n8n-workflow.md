Workflow de Automatización con n8n

Descripción General
Se implementó un workflow automatizado utilizando n8n para procesar datos provenientes de correos electrónicos, transformarlos mediante lógica personalizada y almacenarlos en una arquitectura de datos en la nube.

⚙️Flujo del Proceso
1.Gmail Trigger (API)
- Captura automática de correos entrantes
- Filtrado según criterios definidos

2. Extracción de Datos
- Uso de nodos HTTP / lectura de contenido
- Obtención de datos en formato crudo

3.Procesamiento con JavaScript
- Limpieza de datos
- Estructuración de campos
- Validación de información

4.Envío a Cloud Storage
- Datos crudos enviados mediante HTTP
- Almacenamiento como respaldo (raw layer)

5. Transformación y Carga a BigQuery
- Uso de nodo Execute SQL
- Inserción de datos procesados en tablas estructuradas


🧠Integración con IA (Gemini)
-Uso de modelos Gemini Pro / Flash
- Análisis de datos no estructurados
- Extracción de entidades y generación de campos estructurados

🗄️ Arquitectura de Datos

- Raw Layer: Cloud Storage
- Processed Layer: BigQuery
- Visualization Layer: Looker Studio 

 📊Resultado

- Automatización completa del flujo de datos
- Reducción de procesamiento manual
- Generación de dashboards para toma de decisiones

🛠️Tecnologías

- n8n
- Google Cloud Platform
- BigQuery
- Cloud Storage
- Docker
- JavaScript
- Gemini AI
  
🔍 IMG
<img width="475" height="223" alt="1" src="https://github.com/user-attachments/assets/5d630654-b4fc-490b-abd0-e009e87cbf84" />
<img width="498" height="282" alt="2" src="https://github.com/user-attachments/assets/63ea803a-805a-4469-b51a-6ae19dbf286c" />
<img width="487" height="171" alt="3" src="https://github.com/user-attachments/assets/ec738734-d571-495b-884f-4b41ace2bafe" />

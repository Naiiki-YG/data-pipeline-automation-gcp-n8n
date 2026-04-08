# Pipeline de Datos automatizado con GCP + N8N + IA

## Descripción General

Este proyecto implementa un pipeline de datos end-to-end automatizado, diseñado para capturar, procesar, analizar y visualizar información operativa utilizando infraestructura en la nube e inteligencia artificial.

El sistema permite procesar datos provenientes de correos electrónicos, transformarlos mediante workflows automatizados y enriquecerlos con modelos de IA para su posterior análisis.

## Arquitectura

Gmail → n8n → Cloud Storage → BigQuery → Dashboard  
         ↓  
         IA (Gemini)

## Flujo del proceso

1. **Ingesta de Datos**
   - Captura automática de correos mediante Gmail Trigger en n8n

2. **Procesamiento**
   - Limpieza y estructuración de datos utilizando nodos JavaScript

3. **Almacenamiento (Capa Raw)**
   - Datos crudos almacenados en Google Cloud Storage

4. **Transformación**
   - Procesamiento de datos mediante SQL y carga en BigQuery

5. **Integración con IA**
   - Uso de modelos Gemini para analizar datos no estructurados

6. **Visualización**
   - Creación de dashboards en Looker Studio / Power BI
  
## Uso de Inteligencia Artificial
Se utilizaron modelos Gemini (Pro y Flash) para:

- Analizar datos no estructurados
- Extraer información relevante
- Generar datos estructurados para análisis

## Resultados

- Automatización completa del flujo de datos
- Reducción del procesamiento manual
- Disponibilidad de información para análisis en tiempo real
- Arquitectura escalable en la nube

## Tecnologías Utilizadas

- Google Cloud Platform (Compute Engine, BigQuery, Cloud Storage)
- n8n (automatización de workflows)
- Docker
- JavaScript
- Gemini AI
- Looker Studio / Power BI
  
## 🧩 Diagrama del Pipeline

<img width="1024" height="768" alt="pipeline" src="https://github.com/user-attachments/assets/bf531d5f-0e79-4501-ac81-3b3bb292f55f" />

## Documentación 

- 📄 Infraestructura: docs/setup-gcp-vm.md  
- 🔄 Workflow: docs/n8n-workflow.md
- 📄 Pipeline : docs/pipeline.md

  
## 🎥Demo
Video demostrativo del flujo:
https://drive.google.com/file/d/1Cm47ZJTv4q4nxU6UsI4aDbZLI0SDhd1P/view?usp=sharing

## 🔐 Nota
Por razones de confidencialidad, algunos detalles específicos han sido omitidos.

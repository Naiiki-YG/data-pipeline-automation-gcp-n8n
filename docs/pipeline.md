# Pipeline de Datos Automatizado

## Descripción

Se implementó un pipeline automatizado para procesar correos electrónicos operativos y alertas de seguridad, permitiendo estructurar información no organizada mediante IA y almecenarla en un data warehouse para análisis.

## Flujo General

### 📥 1. Ingesta de Datos
- Fuente: Correos electrónicos (Gmail)
- Procesamiento inicial mediante n8n (Gmail Trigger)

## 🔄 2. Procesamiento Inicial

- Extracción del contenido del correo
- Conversión de archivos adjuntos a formato binario
- Preparación de datos para procesamiento posterior

## 🔀 3. Clasificación de Datos (Nodo IF)

El flujo se divide en dos ramas:

### 🟢 Rama TRUE (Correos con PDF - Cierre de Turno)

#### 3.1 Almacenamiento de archivos
- Subida de PDFs a Google Cloud Storage (capa raw)

#### 3.2 Procesamiento con IA (Gemini)

Se utilizan 3 modelos especializados:

- **IA 1:** Extracción de datos del analista
- **IA 2:** Análisis de observaciones del turno
- **IA 3:** Interpretación de imágenes dentro del PDF

#### 3.3 Unificación de datos
- Generación de ID único
- Consolidación de resultados mediante nodo Set

#### 3.4 Limpieza y transformación
- Procesamiento en JavaScript
- Normalización de datos

#### 3.5 Carga a BigQuery
- Inserción mediante Execute SQL

---

### 🔴 Rama FALSE (Alertas sin PDF)

#### 3.6 Procesamiento de alertas
- Extracción de información desde el cuerpo del correo

#### 3.7 Procesamiento con IA
- Identificación de:
  - Tipo de alerta
  - Cliente afectado
  - Remitente
  - Fecha

#### 3.8 Limpieza de datos
- Normalización mediante JavaScript

#### 3.9 Carga a BigQuery
- Inserción mediante Execute SQL

## 🗄️ 4. Almacenamiento

- **Cloud Storage:** Datos crudos (PDFs)
- **BigQuery:** Datos estructurados

---

## 📊 5. Visualización

- Creación de dashboards en Looker Studio
- Análisis de:
  - Alertas de seguridad
  - Cierres de turno
  - Indicadores operativos

---

## 🚀 Resultado

- Automatización completa del flujo de datos
- Procesamiento inteligente con IA
- Centralización de información en BigQuery
- Disponibilidad de dashboards para toma de decisiones

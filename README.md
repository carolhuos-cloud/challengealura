# 🛒 Asistente Virtual BimBam Buy

## Descripción

Este proyecto implementa un **asistente virtual inteligente basado en Inteligencia Artificial Generativa**, diseñado para responder consultas de clientes utilizando como única fuente de conocimiento documentos oficiales de la empresa ficticia **BimBam Buy**.

La solución utiliza una arquitectura **RAG (Retrieval-Augmented Generation)**, combinando recuperación semántica de información con modelos de lenguaje para generar respuestas contextualizadas, precisas y fundamentadas en la documentación disponible.

El asistente permite consultar información relacionada con procesos de compra, pagos, envíos y políticas comerciales, reduciendo la necesidad de búsqueda manual y mejorando la experiencia del usuario.

La solución fue desarrollada utilizando herramientas de Inteligencia Artificial generativa y desplegada en **Oracle Cloud Infrastructure (OCI)** para habilitar su acceso mediante una interfaz web.

---

# 🏗️ Arquitectura de la solución

El sistema implementa un flujo RAG donde los documentos empresariales son procesados, transformados en representaciones vectoriales y utilizados como fuente de contexto para generar respuestas.

```
Documentos PDF
      │
      ▼
Carga y procesamiento
(PyPDFLoader)
      │
      ▼
Fragmentación de documentos
(Text Splitter)
      │
      ▼
Generación de embeddings
(Sentence Transformers)
      │
      ▼
Base vectorial
(FAISS)
      │
      ▼
Búsqueda semántica
(Retriever)
      │
      ▼
Modelo de lenguaje
(Google Gemini Flash Lite)
      │
      ▼
Respuesta contextualizada
      │
      ▼
Usuario
```

---

# 🔧 Componentes principales

| Componente | Descripción |
|---|---|
| PyPDFLoader | Carga documentos PDF como fuente de conocimiento |
| RecursiveCharacterTextSplitter | Divide documentos en fragmentos procesables |
| Sentence Transformers | Genera embeddings para búsqueda semántica |
| FAISS | Almacena y recupera información relevante |
| LangChain | Orquesta el flujo RAG |
| Google Gemini Flash Lite | Genera respuestas utilizando el contexto recuperado |
| Gradio | Proporciona la interfaz web del asistente |

---

# 🚀 Tecnologías utilizadas

- Python
- LangChain
- Google Gemini API
- Sentence Transformers
- FAISS
- PyPDF
- Gradio
- Oracle Cloud Infrastructure (OCI)

---

# 📂 Estructura del proyecto

```
agente-ia-rag-bimbambuy/

├── app.py
├── AgenteIA_BimBamBuy.ipynb
├── requirements.txt
├── README.md
├── .gitignore
├── documentos/
└── capturas/
```

---

# ⚙️ Instalación

Clonar el repositorio:

```bash
git clone https://github.com/carolhuos-cloud/agente_rag_bimbambuy.git
```

Ingresar al proyecto:

```bash
cd agente-ia-rag-bimbambuy
```

Instalar dependencias:

```bash
pip install -r requirements.txt
```

Configurar la variable de entorno con la API Key de Google Gemini.

Ejecutar la aplicación:

```bash
python app.py
```

---

# 💬 Ejemplos de consultas

## Consulta 1

**Usuario:**

> ¿Cómo puedo acceder al envío gratis?

**Respuesta generada:**

El envío gratis puede estar disponible bajo condiciones promocionales o al alcanzar montos mínimos de compra definidos según el país y campaña vigente.

El beneficio será mostrado antes de finalizar la compra, indicando si el pedido cumple las condiciones necesarias.

---

## Consulta 2

**Usuario:**

> ¿Cómo se calcula el costo del envío?

**Respuesta generada:**

El costo del envío considera factores como:

- Destino del pedido.
- Peso y dimensiones del paquete.
- Servicio de envío seleccionado.
- Promociones vigentes.
- Condiciones para acceder al envío gratuito.

El costo final es mostrado antes de confirmar la compra.

---

## Consulta 3

**Usuario:**

> ¿Se puede cambiar el medio de pago de una orden aprobada?

**Respuesta generada:**

No, como regla general, no es posible cambiar el medio de pago de una orden que ya ha sido aprobada.

---

# 🖥️ Demo

Agregar captura de la interfaz:

```
capturas/interfaz.png
```

---

# ☁️ Despliegue en Oracle Cloud Infrastructure (OCI)

La solución fue desplegada en una instancia de **Oracle Cloud Infrastructure (OCI)** utilizando un entorno cloud para ejecutar la aplicación Python y disponibilizar la interfaz web del asistente.

La arquitectura de despliegue contempla:

```
Usuario
   │
   ▼
Interfaz Gradio
   │
   ▼
Instancia Compute OCI
   │
   ├── Aplicación Python
   ├── Arquitectura RAG
   ├── Modelo IA
   └── Servicios de recuperación
```

## Configuración de infraestructura

- **Cloud Provider:** Oracle Cloud Infrastructure (OCI)
- **Servicio:** Compute Instance
- **Sistema operativo:** Oracle Linux
- **Red:** Virtual Cloud Network (VCN)
- **Interfaz web:** Gradio
- **Puerto de aplicación:** 7860/TCP

Para habilitar el acceso externo se configuraron reglas de seguridad en OCI y en el firewall de la instancia:

- Puerto 22/TCP: acceso remoto mediante SSH.
- Puerto 7860/TCP: acceso a la aplicación web.

La aplicación fue configurada para aceptar conexiones externas mediante:

```python
demo.launch(
    server_name="0.0.0.0",
    server_port=7860
)
```

El despliegue permitió ejecutar el agente RAG en la nube y acceder a la solución mediante un navegador web.

---

# 🔐 Consideraciones para un entorno productivo

Para evolucionar la solución hacia un ambiente empresarial se recomienda:

- Implementar dominio personalizado y HTTPS.
- Configurar Nginx como proxy inverso.
- Implementar monitoreo y trazabilidad de consultas.

---

# 🔮 Mejoras futuras

- Incorporar memoria conversacional.
- Evaluar calidad de respuestas mediante métricas RAG.
- Implementar historial de consultas.
- Agregar autenticación y control de acceso.
- Integrar múltiples fuentes de conocimiento.
- Implementar observabilidad del agente.

---

# 📌 Resultado

El proyecto demuestra la implementación completa de un asistente virtual basado en arquitectura **RAG**, integrando procesamiento documental, búsqueda semántica, modelos de lenguaje e infraestructura cloud.

La solución evidencia la aplicación práctica de Inteligencia Artificial Generativa en un escenario empresarial, desde la construcción del agente hasta su despliegue en Oracle Cloud Infrastructure.

---

# 👩‍💻 Autor

**Carol Huarancay Osorio**

Proyecto desarrollado como parte del **Challenge AlurAgente** de la formación **Tech Builder - Oracle Next Education (ONE) junto con Alura Latam**.

# 🛒 Asistente Virtual BimBam Buy

## Descripción

Este proyecto implementa un asistente virtual basado en Inteligencia Artificial para responder consultas de clientes utilizando únicamente la información contenida en documentos PDF de la empresa ficticia **BimBam Buy**.

El asistente utiliza una arquitectura **RAG (Retrieval-Augmented Generation)**, combinando búsqueda semántica sobre documentos con un modelo de lenguaje para generar respuestas precisas y fundamentadas.

---

## Arquitectura

El flujo de funcionamiento del sistema es el siguiente:

```
Usuario
   │
   ▼
Interfaz web (Gradio)
   │
   ▼
Consulta del usuario
   │
   ▼
FAISS (búsqueda semántica)
   │
   ▼
Fragmentos relevantes de los documentos
   │
   ▼
Gemini Flash Lite
   │
   ▼
Respuesta al usuario
```

### Componentes

- **PyPDFLoader:** carga los documentos PDF.
- **RecursiveCharacterTextSplitter:** divide los documentos en fragmentos.
- **Sentence Transformers:** genera los embeddings.
- **FAISS:** almacena y busca los fragmentos más relevantes.
- **Google Gemini Flash Lite:** genera la respuesta utilizando el contexto recuperado.
- **Gradio:** proporciona una interfaz web sencilla para el usuario.

---

## Tecnologías utilizadas

- Python
- LangChain
- Google Gemini API
- Sentence Transformers
- FAISS
- PyPDF
- Gradio
- Oracle Cloud Infrastructure (OCI)

---

## Estructura del proyecto

```text
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

## Instalación

Clonar el repositorio:

```bash
git clone https://github.com/TU_USUARIO/agente-ia-rag-bimbambuy.git
```

Entrar al proyecto:

```bash
cd agente-ia-rag-bimbambuy
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

Configurar la variable de entorno con la API Key de Google Gemini.

Ejecutar la aplicación:

```bash
python app.py
```

---

## Ejemplos de consultas

### Pregunta

> ¿Cómo puedo acceder al envío gratis?

**Respuesta esperada**

BimBam Buy puede ofrecer envío gratis bajo condiciones promocionales o por montos mínimos de compra definidos por país y campaña. Cuando exista este beneficio, se mostrará antes del pago y podrá aplicarse únicamente a determinadas categorías o regiones.

---

### Pregunta

> ¿Cómo se calcula el costo del envío?

**Respuesta esperada**

El costo del envío depende del destino, peso volumétrico, tamaño del paquete, servicio elegido y las promociones vigentes.

---

### Pregunta

> ¿Se puede cambiar el medio de pago de una orden aprobada?

**Respuesta esperada**

No. Como regla general, una orden aprobada no permite cambiar el medio de pago.

---

### Pregunta

> ¿Qué sucede si el pago aparece pendiente?

**Respuesta esperada**

Puede tratarse de una conciliación en curso o una autorización temporal. Se recomienda esperar la confirmación del estado de la transacción.

---

## Capturas

### Interfaz del asistente

Agregar aquí una captura de la aplicación.

```
capturas/interfaz.png
```

---

## Despliegue en Oracle Cloud Infrastructure (OCI)

Una vez desplegada la aplicación, agregar:

- URL pública de OCI.

o

- Captura de pantalla de la aplicación ejecutándose.

Ejemplo:

```
https://TU-APLICACION.oraclecloudapps.com
```

---

## Autor

**Carol Huarancay Osorio**

Proyecto desarrollado como parte del curso de Agentes de Inteligencia Artificial.

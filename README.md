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

¡Hola! Es un gusto saludarte. Como asistente virtual de BimBam Buy, con gusto te informo sobre cómo funciona el envío gratis en nuestra plataforma:

El envío gratis puede estar disponible bajo condiciones promocionales o al alcanzar montos mínimos de compra, los cuales son definidos según el país y la campaña vigente.

Para acceder a este beneficio, ten en cuenta lo siguiente:
* **Visualización:** El envío gratis se mostrará claramente antes de realizar el pago.
* **Condiciones:** Puede aplicar únicamente a categorías o regiones determinadas.
* **Vigencia:** Este beneficio puede tener límites de tiempo o de stock.
* **Consideración importante:** El envío gratis no cubre necesariamente los costos de reenvío si estos son atribuibles al cliente.

Te recomiendo revisar las promociones vigentes antes de finalizar tu compra para verificar si tu pedido califica para este beneficio. ¡Quedo a tu disposición si tienes alguna otra duda!

---

### Pregunta

> ¿Cómo se calcula el costo del envío?

**Respuesta esperada**

¡Hola! Con gusto te explico cómo se determina el costo de envío en BimBam Buy.

El costo de tu envío se calcula considerando los siguientes factores:

*   **Destino:** La ubicación a donde se enviará el paquete.
*   **Peso volumétrico:** El peso y dimensiones del paquete.
*   **Tamaño del paquete:** Las medidas físicas del mismo.
*   **Servicio elegido:** La modalidad de envío seleccionada.
*   **Promociones vigentes:** Cualquier oferta activa que pueda aplicar.
*   **Umbral de envío gratis:** Si tu compra califica para envío gratuito según los montos mínimos definidos por país y campaña.

**Información importante:**
El costo final de tu envío se mostrará siempre antes de que confirmes tu compra, para que tengas total claridad antes de realizar el pago. Ten en cuenta que, en situaciones excepcionales, podría haber una corrección posterior, siempre que esté debidamente justificada.

Si tienes alguna otra duda, ¡estoy aquí para ayudarte!

---

### Pregunta

> ¿Se puede cambiar el medio de pago de una orden aprobada?

**Respuesta esperada**

No, como regla general, no es posible cambiar el medio de pago de una orden que ya ha sido aprobada.
---

### Pregunta

> ¿Qué sucede si el pago aparece pendiente?

**Respuesta esperada**

Si tu orden figura como pendiente de pago, esto puede deberse a alguna de las siguientes razones:

*   La confirmación aún está en proceso.
*   Se está realizando una validación antifraude.
*   Hubo un error de conexión.
*   La sesión expiró.
*   El pago fue iniciado, pero no se finalizó correctamente.

Además, si el estado específico es "pendiente de conciliación", te informamos que estamos revisando el estado de la orden y te confirmaremos la situación cuanto antes.

**Recomendaciones:**
*   No repitas el pago sin antes revisar el estado de tu orden.
*   Si necesitas asistencia adicional, puedes contactar a soporte proporcionando los detalles de tu transacción (orden asociada, medio de pago, hora del evento y monto) para que podamos brindarte una respuesta precisa sobre el estado actual, la causa probable y el plazo estimado de resolución.
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

el proyecto es parte del Challenge AlurAgente en la formación Tech Builder del programa Oracle Next Education (ONE) junto con Alura Latam

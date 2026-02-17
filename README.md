# 🚀 AI Engineer Roadmap — De Full Stack a AI Engineer en 14 Semanas

<div align="center">

![AI Engineer](https://img.shields.io/badge/AI_Engineer-Roadmap-blue?style=for-the-badge&logo=openai&logoColor=white)
![Duration](https://img.shields.io/badge/Duration-14_Weeks-green?style=for-the-badge)
![Hours](https://img.shields.io/badge/Total-308_Hours-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow?style=for-the-badge)

**Plan de estudio práctico para transicionar de Full Stack Developer a AI Engineer,
construyendo features reales sobre [MINCA Inventory System](https://github.com/tu-usuario/minca-inventory-system).**

[Timeline](#-timeline) · [Roadmap Visual](#%EF%B8%8F-roadmap-visual) · [Recursos](#-recursos-esenciales) · [Portfolio](#-portfolio-output)

</div>

---

## 📖 Sobre Este Plan

Este roadmap está diseñado para **developers Full Stack con experiencia** que quieren posicionarse como **AI Engineers** en el mercado remoto USA/Europa. No es un curso teórico — cada semana produce features reales sobre una aplicación en producción.

### ¿Por Qué AI Engineer y No ML Engineer?

| | AI Engineer | ML Engineer |
|---|---|---|
| **Foco principal** | Construir productos con AI integrada | Entrenar y optimizar modelos |
| **Día a día** | RAG, agents, LLM integration, APIs | Notebooks, pipelines de datos, experiments |
| **Requisitos típicos** | 2-3 años dev + AI skills | 3-5 años ML + Master's/PhD |
| **Ventaja para Full Stack** | ✅ Tu experiencia es tu diferenciador | ❌ Compites contra PhDs |
| **Demanda 2026** | 📈 Explotando (toda empresa quiere AI) | 📊 Estable (roles más nicho) |
| **Salario remoto (junior-mid)** | $120-170K USD | $130-180K USD |

### Stack del Plan

```
Frontend:  React 19 · TypeScript · Tailwind CSS
Backend:   FastAPI · Python · Supabase (PostgreSQL + pgvector)
AI/LLM:    LangGraph · LangChain · OpenAI API · Anthropic API
ML:        scikit-learn · XGBoost · Isolation Forest
Infra:     Docker · MCP (Model Context Protocol) · Whisper · Sentry
```

---

## 🗺️ Roadmap Visual

```
Semana    1    2    3    4    5    6    7    8    9    10   11   12   13   14
        |--------|-----------------|----------------------|-------------|--------|
        | FASE 0 |     FASE 1      |       FASE 2         |   FASE 3    | FASE 4 |
        |ML + LLM|   RAG System    |   Agentic AI + MCP   |ML + Produc. |Deploy  |
        |Fundamen|   Production    |   Multi-Agent Voice   |Predictions  |Intervw |
        |  tos   |    Ready        |   Image · Protocol    |Monitoring   |Portfolio|
```

---

## 📅 Timeline

### Fase 0 — Fundamentos (Semanas 1-2) · `44h`

> *"No necesitas ser ML Engineer, pero sí entender lo que usas"*

<details>
<summary><b>Semana 1: ML Core — Lo Esencial</b></summary>

#### Día 1-2: Matemáticas Mínimas Necesarias (6h)

**Temas:**
- **Vectores y embeddings**: qué es un vector, por qué un embedding de 1536 dimensiones representa significado
- **Cosine similarity**: cómo se mide la "cercanía" entre dos textos — lo usarás todos los días en RAG
- **Probabilidad básica**: distribuciones, Bayes theorem (intuición, no fórmulas)
- **Gradient descent**: intuición visual de cómo "aprende" un modelo

**Recursos:**
- [3Blue1Brown — Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) (primeros 5 videos)
- [StatQuest — Gradient Descent](https://www.youtube.com/watch?v=sDv4f4s2SB8)
- [Jay Alammar — The Illustrated Word2Vec](https://jalammar.github.io/illustrated-word2vec/)

**Entregable:** Jupyter notebook generando embeddings de repuestos de MINCA, calculando cosine similarity, y mostrando repuestos "semánticamente similares"

---

#### Día 3-4: Modelos Clásicos que Debes Conocer (6h)

**Temas:**
- Supervised vs Unsupervised: clasificación, regresión, clustering
- Regresión logística: tu baseline para clasificación
- Random Forest y XGBoost: los más usados en producción para datos tabulares
- K-Means: para segmentación y clustering
- **Métricas de evaluación**: accuracy, precision, recall, F1, AUC-ROC, MAE, RMSE — SALE EN ENTREVISTAS
- Overfitting: qué es, por qué pasa, cómo prevenirlo

**Recursos:**
- [Scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)
- [StatQuest ML playlist](https://www.youtube.com/playlist?list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF)
- "Hands-On ML" de Géron — Capítulos 1-4

**Entregable:** Notebook comparando 3 modelos (LogReg, RF, XGBoost) sobre datos de MINCA: "¿Se agota este repuesto en 7 días?"

---

#### Día 5: Feature Engineering Básico (3h)

**Temas:**
- Encoding: one-hot, label encoding
- Feature creation: variables derivadas de datos existentes
- sklearn Pipeline y ColumnTransformer

**Implementación en MINCA — Pipeline desde tabla `movements`:**
- Rotación por item (movimientos/semana)
- Velocidad de consumo (promedio de egresos)
- Días hasta quiebre (stock / velocidad)
- Patrones por día de semana

---

#### Fin de semana (7h)
- Revisión + notas para entrevistas
- 2 problemas LeetCode Easy/Medium
- Commits limpios a GitHub

</details>

<details>
<summary><b>Semana 2: LLMs — Cómo Funcionan</b></summary>

#### Día 1-2: Anatomía de un LLM (6h)

**Temas:**
- **Tokenización**: cómo texto se convierte en números. Por qué importa el context window limit
- **Attention mechanism**: intuición de "el modelo aprende qué partes del input importan"
- **Context window**: qué es, límites, implicaciones prácticas para RAG
- **Temperature y sampling**: por qué respuestas varían. Cuándo temperature 0 vs 0.7
- **Embeddings en detalle**: cómo se generan, dimensiones, uso en búsqueda semántica

**Recursos:**
- [Jay Alammar — The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) — ESENCIAL
- [Andrej Karpathy — Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY) (para entender, no implementar)

**Entregable:** Documento de 1-2 páginas explicando: cómo un LLM procesa un prompt, por qué RAG existe, qué es un embedding

---

#### Día 3-4: Prompt Engineering Avanzado (6h)

**Temas:**
- Zero-shot vs Few-shot prompting
- Chain-of-thought: "piensa paso a paso"
- **Structured output**: forzar JSON/XML — CRÍTICO para aplicaciones
- System prompts, prompt templating, output parsing

**Implementación en MINCA — módulo `prompts/`:**
1. Clasificar solicitudes por urgencia → `{urgency: "high", reason: "..."}`
2. Generar resúmenes semanales de movimientos de stock
3. Extraer entidades: "5 pastillas de freno para Bogotá Norte" → JSON estructurado

---

#### Día 5: APIs de LLM y SDK (3h)

**Temas:**
- OpenAI API: completions, embeddings, function calling
- Anthropic API: messages, tool use, structured outputs
- Error handling: retries, timeouts, fallbacks entre proveedores
- Streaming responses

**Implementación en MINCA:**
Servicio `ai_service.py` en FastAPI: abstrae proveedor (OpenAI/Anthropic), retry con exponential backoff, streaming, logging de todas las llamadas

---

#### Fin de semana (7h)
- Practica explicar Transformer en voz alta
- 2 problemas LeetCode
- Push limpio a GitHub

</details>

---

### Fase 1 — RAG System Production-Ready (Semanas 3-5) · `66h`

> *"El patrón #1 en AI enterprise — y tu feature más impresionante"*

<details>
<summary><b>Semana 3: RAG Fundamentals + Implementación Base</b></summary>

#### Día 1: Teoría RAG Completa (3h)

**Pipeline:** Document Loading → Chunking → Embedding → Vector Store → Retrieval → Generation

**Temas:**
- Chunking strategies: fixed-size, recursive, semantic — trade-offs
- Embedding models: OpenAI `text-embedding-3-small`, sentence-transformers
- Vector stores: pgvector (ya en Supabase), ChromaDB, Pinecone
- Retrieval: similarity search, MMR (Maximum Marginal Relevance)

---

#### Día 2-3: Ingesta de Documentos de MINCA (6h)

**Documentos a ingestar:**
- Políticas de garantía (condiciones, plazos)
- Procedimientos de taller (solicitudes, reclamos)
- Catálogo de repuestos (descripciones, compatibilidades)
- FAQ del negocio

**Schema en Supabase:**
```sql
CREATE TABLE document_chunks (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    document_name TEXT NOT NULL,
    document_type TEXT NOT NULL,
    chunk_text TEXT NOT NULL,
    chunk_index INTEGER NOT NULL,
    embedding VECTOR(1536),
    metadata JSONB,
    created_at TIMESTAMPTZ DEFAULT now()
);
```

---

#### Día 4-5: Retrieval + Generation Pipeline (6h)

**Endpoint:** `POST /api/v1/ai/ask`
```json
{
  "question": "¿Cuál es la política de garantía para baterías de litio?"
}
```

```json
{
  "answer": "La garantía para baterías de litio cubre...",
  "sources": [{"document": "Política de Garantías v2", "similarity": 0.89}],
  "confidence": 0.92
}
```

**Guardrails:**
- Similarity > 0.7, si no: "No tengo información suficiente"
- Nunca inventar información fuera de los documentos
- Citar fuente exacta

---

#### Fin de semana (7h)
- 20+ pares pregunta/respuesta para evaluación
- Medir: accuracy, relevancia, hallucination rate
- Documentar arquitectura

</details>

<details>
<summary><b>Semana 4: RAG Avanzado — Nivel Producción</b></summary>

#### Día 1-2: Hybrid Search + Reranking (6h)

**Por qué hybrid:** semántica captura significado, keywords captura términos exactos (códigos de repuesto, números de serie)

**Implementación:**
1. Columna `tsvector` para full-text search en PostgreSQL
2. Hybrid scoring: `0.7 * semantic_score + 0.3 * keyword_score`
3. Metadata filtering: "buscar solo en garantías" o "solo taller X"
4. Reranking con cross-encoder (`ms-marco-MiniLM-L-6-v2`)

---

#### Día 3-4: Evaluación Automática del RAG (6h)

- Dataset: 50+ pares (pregunta, respuesta_esperada, contexto_correcto)
- Evaluación con RAGAS o LLM-as-judge
- Script: `Accuracy: 87%, Faithfulness: 92%, Mean Latency: 1.2s`
- Tabla `rag_evaluations` para tracking histórico

---

#### Día 5: UI de RAG en MINCA (3h)

**React:** Nueva página `/ai/assistant`
- Chat con streaming (typewriter effect)
- Sección "Fuentes" con highlight del chunk relevante
- Feedback: 👍👎 por respuesta
- Filtro: Garantías | Procedimientos | Catálogo | Todo

</details>

<details>
<summary><b>Semana 5: Text-to-SQL — El Feature Estrella</b></summary>

**Endpoint:** `POST /api/v1/ai/query`
```json
{ "question": "¿Cuántas pastillas de freno hay en Bogotá Norte?" }
```

```json
{
  "answer": "Actualmente hay 23 unidades en Bogotá Norte.",
  "sql_generated": "SELECT SUM(quantity) FROM stock JOIN...",
  "data": [{"total": 23}],
  "execution_time_ms": 145
}
```

#### Guardrails de Seguridad (no negociables)

| Guardrail | Implementación |
|---|---|
| Whitelist de tablas | Solo `inventory`, `stock`, `movements`, `locations`, `spares` |
| Read-only | Solo SELECT — prohibido INSERT, UPDATE, DELETE, DROP |
| SQL validation | Parsear con `sqlparse` antes de ejecutar |
| Timeout | Máximo 5 segundos |
| Rate limiting | 20 queries/minuto por usuario |
| Row limit | `LIMIT 100` automático |
| Logging | Cada query se guarda para auditoría |

**Evaluación:** 30+ preguntas → SQL esperado, medir correctness % y execution success %

</details>

---

### Fase 2 — Agentic AI + MCP (Semanas 6-9) · `88h`

> *"Donde los AI Engineers se separan de los que solo llaman APIs"*

<details>
<summary><b>Semana 6: LangGraph — Multi-Agent Orchestration</b></summary>

#### Arquitectura del Sistema Multi-Agent

```
Usuario → Supervisor → Routing Decision
                        ├→ SQL Agent       → DB Query        → Response
                        ├→ RAG Agent       → Vector Search   → Response
                        ├→ Action Agent    → API Call         → Confirm → Execute
                        └→ Analytics Agent → ML Prediction   → Response
          Supervisor ← Combine Responses → Usuario
```

#### 4 Agents Especializados

| Agent | Especialidad | Herramientas | Ejemplo |
|---|---|---|---|
| **SQL Agent** | Datos cuantitativos | SELECT queries | "¿Cuántos repuestos se usaron ayer?" |
| **RAG Agent** | Conocimiento documental | Vector search | "¿Cuál es el procedimiento de garantía?" |
| **Action Agent** | Ejecutar acciones | Create, update | "Crea solicitud de 10 pastillas" |
| **Analytics Agent** | Predicciones | ML endpoints | "¿Qué se agota esta semana?" |

**Testing:** 20+ escenarios, medir routing accuracy y end-to-end success rate

</details>

<details>
<summary><b>Semana 7: Tool Use Avanzado y Function Calling</b></summary>

#### Herramientas del Action Agent

```python
create_spare_request(item_id, quantity, location_id, urgency, reason)
check_stock_levels(item_id=None, location_id=None)
register_movement(item_id, quantity, from_location, to_location, reason)
generate_report(report_type, location_id, date_range)
send_notification(recipient_id, message, channel)
```

#### Conversaciones Multi-turno
- **Conversation memory**: historial por usuario en `conversation_history`
- **Context window management**: resumir turnos anteriores
- **Flujo ejemplo**: "¿Cuántas pastillas hay?" → "Están bajas" → "Crea solicitud" → "Solicitud #1234 creada"

</details>

<details>
<summary><b>Semana 8: MCP — Model Context Protocol</b></summary>

**¿Qué es MCP?** El "USB para AI" — estándar abierto (Anthropic → Linux Foundation) para conectar AI con herramientas externas.

#### MCP Server para MINCA

**Resources (datos):**
- `minca://inventory/{location_id}` → stock por ubicación
- `minca://movements/recent` → últimos movimientos
- `minca://spares/catalog` → catálogo de repuestos
- `minca://analytics/stock-risk` → repuestos en riesgo

**Tools (acciones):**
- `query_inventory` · `create_request` · `search_documents` · `get_forecast`

**Resultado:** Claude Desktop, IDEs, y cualquier AI client compatible pueden interactuar con MINCA

</details>

<details>
<summary><b>Semana 9: Voice + Multimodal</b></summary>

#### Pipeline de Voz
```
Audio → Whisper (STT) → Texto → Agent System → Respuesta → TTS → Audio
```

#### Procesamiento de Imágenes
Técnico toma foto de repuesto dañado → Vision API identifica tipo → sugiere reemplazo

**Endpoint:** `POST /api/v1/ai/identify-part`

#### Interfaces Unificadas
El assistant acepta texto, voz e imágenes — todo pasa por el mismo multi-agent system

</details>

---

### Fase 3 — ML Aplicado + Producción (Semanas 10-12) · `66h`

> *"Predicciones reales + todo lo que hace falta para producción"*

<details>
<summary><b>Semana 10: Modelos de Predicción</b></summary>

#### 3 Modelos sobre Datos Reales de MINCA

| Modelo | Tipo | Target | Algoritmo | Métrica |
|---|---|---|---|---|
| Stock-out prediction | Clasificación | ¿Se agota en 7 días? | XGBoost | Precision/Recall |
| Demand forecasting | Regresión | Unidades/semana | XGBoost | MAE |
| Anomaly detection | No supervisado | ¿Movimiento inusual? | Isolation Forest | Anomaly score |

**Endpoints FastAPI:**
- `GET /api/v1/analytics/stock-risk`
- `GET /api/v1/analytics/demand-forecast?item_id=X&location_id=Y`
- `GET /api/v1/analytics/anomalies`

**Dashboard React:** `/analytics` con cards + gráficos

</details>

<details>
<summary><b>Semana 11: AI en Producción</b></summary>

#### Observability
```sql
-- Tabla ai_logs
-- request_id, user_id, agent_type, prompt_tokens, completion_tokens,
-- latency_ms, cost_usd, user_feedback, created_at
```
- Dashboard: uso diario, costo acumulado, satisfaction rate
- Alertas: error rate > 5% o latencia > 5s

#### Optimización de Costos
- **Semantic cache**: similarity > 0.95 → devolver cache
- **Rate limiting**: 50 AI queries/día por usuario
- **Provider fallback**: OpenAI caído → Anthropic automáticamente

#### Testing de AI Systems
- Unit tests por tool · Integration tests · Regression tests en CI/CD

</details>

<details>
<summary><b>Semana 12: Alertas Proactivas + Copilot</b></summary>

#### Alertas Inteligentes
Cron job diario → predicciones → repuesto en riesgo → LLM genera mensaje → envía notificación

#### Resúmenes Ejecutivos
Reporte semanal por taller generado por LLM + datos reales

#### Copilot UX
Widget flotante + sugerencias contextuales + quick actions

</details>

---

### Fase 4 — Portfolio + Entrevistas (Semanas 13-14) · `44h`

> *"Empaqueta todo para que impresione"*

<details>
<summary><b>Semana 13: Deploy y Documentación</b></summary>

- **Deploy:** FastAPI → Render | React → Vercel | Supabase producción
- **README:** Architecture, Features, Tech Stack, ML Metrics, API Docs
- **Video demo** 3-5 min: RAG + Text-to-SQL + Voice + Agents + MCP
- **LinkedIn:** "AI Engineer | Building AI-Powered Products with LLMs, RAG & Agents"

</details>

<details>
<summary><b>Semana 14: Preparación de Entrevistas</b></summary>

#### Preguntas que Podrás Responder

**RAG:** "¿Cómo implementaste RAG?" → Pipeline, hybrid search, reranking, eval 50+ queries, faithfulness > 85%

**Agents:** "¿Cómo diseñaste tu multi-agent system?" → Supervisor routing, 4 agents, LangGraph, human-in-the-loop

**MCP:** "¿Qué es MCP?" → Estándar abierto, interoperabilidad, cualquier AI client usa mi sistema

**ML:** "¿Por qué XGBoost?" → Mejor F1 vs RF, gradient boosting vs bagging, feature importance

**Producción:** "¿Cómo reduces costos?" → Semantic cache, rate limiting, provider fallback

**Seguridad:** "¿Text-to-SQL seguro?" → Whitelist, read-only, SQL parsing, timeout, rate limit, logging

#### System Design con AI
- Customer support con AI
- RAG para 10M documentos
- Sistema de recomendaciones e-commerce

#### Plataformas para Aplicar
LinkedIn · Turing · Toptal · RemoteRocketship · BuiltIn · AngelList

</details>

---

## ✅ Skills Checklist

### LLM Engineering
- [ ] Cómo funcionan los LLMs (tokenización, attention, context window)
- [ ] Prompt Engineering avanzado (few-shot, CoT, structured output)
- [ ] OpenAI API y Anthropic API
- [ ] Streaming responses
- [ ] Function calling / Tool use
- [ ] Error handling y fallbacks

### RAG (Retrieval Augmented Generation)
- [ ] Pipeline: ingest → chunk → embed → store → retrieve → generate
- [ ] Chunking strategies (recursive, semantic)
- [ ] Embedding models y vector stores (pgvector)
- [ ] Hybrid search (semantic + keyword)
- [ ] Reranking con cross-encoders
- [ ] Evaluación automatizada (RAGAS, LLM-as-judge)
- [ ] Text-to-SQL con guardrails de seguridad

### Agentic AI
- [ ] AI Agents: ReAct pattern, planning, tool use
- [ ] LangGraph: grafos de estados, routing, supervisors
- [ ] Multi-agent orchestration
- [ ] MCP (Model Context Protocol): server, resources, tools
- [ ] Conversation memory y session management
- [ ] Human-in-the-loop para acciones críticas

### ML Clásico Aplicado
- [ ] Supervised vs Unsupervised learning
- [ ] XGBoost, Random Forest, Logistic Regression
- [ ] Métricas: Precision, Recall, F1, AUC-ROC, MAE
- [ ] Feature Engineering y sklearn Pipelines
- [ ] Model serialization y serving con FastAPI
- [ ] Overfitting, cross-validation, regularización

### AI en Producción
- [ ] Logging y observability (ai_logs, cost tracking)
- [ ] Semantic caching
- [ ] Rate limiting y security
- [ ] Testing de AI systems (unit, integration, regression)
- [ ] Monitoring y alerting
- [ ] Provider fallback

### Multimodal
- [ ] Speech-to-Text (Whisper)
- [ ] Text-to-Speech
- [ ] Vision (análisis de imágenes con LLMs)

---

## 🏗️ Arquitectura Final

```
+-------------------------------------------------------------------+
|                        INTERFACES                                  |
|   React PWA: Chat (texto) | Voice (Whisper) | Camera (Vision)     |
+-------------------------------+-----------------------------------+
                                |
+-------------------------------v-----------------------------------+
|                     ORCHESTRATION                                  |
|              LangGraph Supervisor (routing)                        |
|      +-----------+-----------+------------+-----------+           |
|      | SQL Agent | RAG Agent |Action Agent| Analytics |           |
|      | (queries) |  (docs)   |(mutations) | (predict) |           |
|      +-----------+-----------+------------+-----------+           |
+-------------------------------+-----------------------------------+
                                |
+-------------------------------v-----------------------------------+
|                       AI LAYER                                     |
|   LLMs (Claude/GPT-4) | Embeddings | ML Models (XGBoost)          |
+-------------------------------+-----------------------------------+
                                |
+-------------------------------v-----------------------------------+
|                      DATA LAYER                                    |
|   Supabase PostgreSQL + pgvector                                   |
|   document_chunks | ai_logs | ai_cache | conversation_history      |
+-------------------------------+-----------------------------------+
                                |
+-------------------------------v-----------------------------------+
|                    INTEGRATIONS                                    |
|   MCP Server | FastAPI REST | WhatsApp | Email Reports             |
+-------------------------------------------------------------------+
```

---

## 💼 Portfolio Output

Al completar las 14 semanas tendrás:

### MINCA AI — Intelligent Spare Parts Management Platform

| Sub-proyecto | Descripción | Skills |
|---|---|---|
| **RAG Knowledge System** | Pipeline RAG con hybrid search, reranking y evaluación automatizada | RAG, pgvector, embeddings, eval |
| **Multi-Agent Orchestration** | 4 agents con LangGraph supervisor | LangGraph, tool use, function calling |
| **MCP Integration** | MCP server exponiendo datos y acciones | MCP protocol, interoperability |
| **Predictive Analytics** | XGBoost models: stock prediction, demand forecast, anomalies | ML, FastAPI serving, feature eng |
| **Multimodal Interface** | Voice (Whisper + TTS) e image (Vision) interfaces | Whisper, multimodal, WebSockets |

### Métricas Target
- RAG faithfulness **> 85%**
- Text-to-SQL accuracy **> 90%**
- Agent routing accuracy **> 95%**
- ML models con métricas documentadas
- Video demo de 3-5 minutos
- MCP server publicado en GitHub

---

## 📚 Recursos Esenciales

### Libros
| Libro | Para qué | Capítulos |
|---|---|---|
| Hands-On ML — Géron | ML clásico | Cap 1-7 |
| Designing ML Systems — Chip Huyen | Producción | Todo |

### Cursos Gratuitos
- [3Blue1Brown: Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) (3h)
- [StatQuest: ML playlist](https://www.youtube.com/@statquest) (seleccionar videos)
- [DeepLearning.AI: LangChain for LLM Apps](https://www.deeplearning.ai/short-courses/langchain-for-llm-application-development/) (gratis)
- [DeepLearning.AI: Building Agentic RAG](https://www.deeplearning.ai/short-courses/) (gratis)

### Documentación
- [LangGraph](https://langchain-ai.github.io/langgraph/) · [MCP](https://modelcontextprotocol.io) · [Anthropic Tool Use](https://docs.anthropic.com/en/docs/tool-use) · [pgvector](https://github.com/pgvector/pgvector)

### Blogs Esenciales
- [Jay Alammar — The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- [Chip Huyen — Building LLM Apps](https://huyenchip.com/blog/)
- [Anthropic — Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)

### Para Entrevistas
- [Chip Huyen ML Interview Questions](https://github.com/chiphuyen/ml-interviews-book) (GitHub)
- [Introduction to Statistical Learning](https://www.statlearning.com/) Cap 2-5 (gratis online)

---

## 📊 Progreso

| Fase | Semanas | Horas | Estado |
|---|---|---|---|
| Fase 0: Fundamentos ML + LLM | 1-2 | 44h | ⬜ No iniciado |
| Fase 1: RAG System | 3-5 | 66h | ⬜ No iniciado |
| Fase 2: Agentic AI + MCP | 6-9 | 88h | ⬜ No iniciado |
| Fase 3: ML + Producción | 10-12 | 66h | ⬜ No iniciado |
| Fase 4: Portfolio + Entrevistas | 13-14 | 44h | ⬜ No iniciado |
| **Total** | **14** | **308h** | |

---

## 📝 Notas

- Asume **22 horas/semana** de dedicación
- Todo se implementa sobre **MINCA Inventory System** — una app real en producción
- Prioriza skills que buscan empresas **USA/Europa en 2026** para AI Engineer remoto
- Basado en análisis de +100 job postings en RemoteRocketship, Glassdoor, BuiltIn, Indeed

---

<div align="center">

**🧠 De Full Stack Developer a AI Engineer en 14 semanas**

*Construyendo features reales, no tutoriales.*

</div>
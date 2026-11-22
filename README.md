# TFM — Agente conversacional ReAct para atención bancaria en Ecuador

**Autora:** Johanna Elizabeth García Mora  
**Director:** Joaquín Gaspar Medina Arco  
**Institución:** Universidad Internacional de La Rioja (UNIR)  
**Máster:** Máster Universitario en Inteligencia Artificial  
**Versión inmutable:** v2.0

---

## Descripción

Evaluación experimental de un agente conversacional basado en el paradigma ReAct (Yao et al., 2023) para la atención de consultas bancarias en Ecuador. El agente utiliza LangGraph + LangChain con el modelo `openai/gpt-oss-20b` a través de la API de Groq, comparado contra un sistema de referencia basado en reglas (baseline_v2).

**Experimento:** 18 escenarios Banking77-EC × 2 sistemas × 3 repeticiones = **108 ejecuciones totales**

---

## Requisitos

- Python 3.10+
- Cuenta en [Groq](https://console.groq.com/) (plan gratuito suficiente)
- Google Colab o entorno local con Jupyter

### Dependencias principales

```
langchain
langchain-openai
langgraph
groq
spacy
```

Instalar con:
```bash
pip install langchain langchain-openai langgraph groq spacy
python -m spacy download es_core_news_sm
```

---

## Configuración

Crear la variable de entorno con tu clave de Groq:

```python
import os
os.environ["GROQ_API_KEY"] = "tu_clave_aqui"
```

**Nunca incluir la clave directamente en el código.**

---

## Ejecución

1. Abrir TFM_Agente_ReAct_Banking_v1.ipynb en Google Colab o Jupyter
2. Ejecutar las celdas en orden
3. El notebook ejecuta los 18 escenarios para el agente ReAct y baseline_v2
4. Los resultados incluyen: cobertura léxica, latencia, uso de herramientas y análisis estadístico (Wilcoxon)

---

## Estructura del repositorio

```
tfm-react-agent-banking/
├── TFM_Agente_ReAct_Banking_v1.ipynb   # Notebook principal del experimento
└── README.md
```

---

## Resultados principales

| Sistema | Cobertura léxica media | p-valor | Tamaño del efecto (r) |
|---|---|---|---|
| Agente ReAct | 33,8 % | 0,023 | 0,54 |
| Baseline_v2 | 10,6 % | — | — |

---

## Referencia

Yao, S., Zhao, J., Yu, D., Du, N., Shafran, I., Narasimhan, K., & Cao, Y. (2023). ReAct: Synergizing reasoning and acting in language models. *ICLR 2023*.

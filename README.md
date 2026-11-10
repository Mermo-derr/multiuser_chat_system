# Chat multiusuario con memoria

Chatbot en Streamlit con LangGraph en el que cada usuario tiene sus propios chats y una memoria a largo plazo compartida entre todos sus chats.

## Requisitos

- Python 3.14
- Una clave de API de OpenAI

## Instalación

Desde la carpeta del proyecto, en PowerShell:

```powershell
py -3.14 -m venv venv
venv\Scripts\python.exe -m pip install streamlit langchain-core langchain-openai langchain-chroma langgraph langgraph-checkpoint-sqlite chromadb pydantic typing_extensions
```

## Ejecución

Este proyecto no carga un archivo `.env`, así que la clave debe estar definida en la terminal:

```powershell
$env:OPENAI_API_KEY = "tu_clave"
venv\Scripts\streamlit.exe run app.py
```

Se abre en http://localhost:8501.

## Datos

Todo se guarda en `users/<usuario>/`, que se crea automáticamente y no se sube al repositorio:

- `langgraph_memory.db`: historial de cada chat.
- `chromadb/`: recuerdos a largo plazo del usuario.

El modelo, la temperatura y las categorías de memoria se cambian en `config.py`.

# 🤖 Modular LLM Agent Chatbot

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-Purple?style=for-the-badge)

A powerful, modular AI chatbot built with a **FastAPI** backend and **Streamlit** frontend. It leverages **LangGraph** for orchestrating agentic workflows and supports multiple LLM providers including **Groq** and **OpenAI**, with optional real-time web search capabilities via **Tavily**.

---

## 🚀 Features

-   **Modular Design**: Decoupled architecture with a dedicated API backend and a reactive UI frontend.
-   **Multi-Provider Support**: Seamlessly switch between **Groq** (Llama 3, Mixtral) and **OpenAI** (GPT-4o Mini) models.
-   **Intelligent Refinement**: Uses **LangGraph** `create_react_agent` to build agents that reason and act.
-   **Web Search Capable**: Integrated **Tavily Search API** allows the agent to fetch real-time information from the web.
-   **Customizable Personas**: Dynamically inject system prompts to alter the agent's personality and behavior.

## 🛠️ Tech Stack

-   **Backend**: [FastAPI](https://fastapi.tiangolo.com/) - High-performance web framework for building APIs.
-   **Frontend**: [Streamlit](https://streamlit.io/) - Rapidly builds data apps and UIs.
-   **Orchestration**: [LangGraph](https://langchain-ai.github.io/langgraph/) & [LangChain](https://www.langchain.com/) - Framework for building stateful, multi-actor applications with LLMs.
-   **Search**: [Tavily API](https://tavily.com/) - Search engine optimized for LLMs.
-   **Validation**: [Pydantic](https://docs.pydantic.dev/) - Data validation and settings management.

## 📂 Project Structure

```bash
Modular-LLM-Agent-Chatbot/
├── ai_agent.py      # Core agent logic using LangGraph and LangChain
├── backend.py       # FastAPI server handling chat endpoints
├── frontend.py      # Streamlit user interface
├── requirements.txt # Project dependencies
├── Pipfile          # Pipenv dependency file
├── .env             # Environment variables (API Keys)
└── .gitignore       # Git configuration
```

## ⚡ Setup & Installation

### 1. Clone the Repository
```bash
git clone <repository_url>
cd Modular-LLM-Agent-Chatbot
```

### 2. Configure Environment Variables
Create a `.env` file in the root directory. You can use the example below:

```env
GROQ_API_KEY=gsk_...
OPENAI_API_KEY=sk-...
TAVILY_API_KEY=tvly-...
```

### 3. Install Dependencies
You can use either **Pipenv** (recommended) or **pip**.

**Option A: Using Pipenv**
```bash
pipenv install
pipenv shell
```

**Option B: Using pip**
```bash
pip install -r requirements.txt
```

## 🏃‍♂️ Running the Application

This is a two-part application. You need to run the backend and frontend in separate terminal windows.

### Step 1: Start the Backend (API)
The backend service handles the logic and model communication.
```bash
python backend.py
```
> The API will start at `http://127.0.0.1:9999`
>
> 📄 **Swagger Specs**: Visit `http://127.0.0.1:9999/docs` to test endpoints interactively.

### Step 2: Start the Frontend (UI)
The frontend connects to the backend API to provide a chat interface.
```bash
streamlit run frontend.py
```
> The UI will open automatically in your browser at `http://localhost:8501`.

## 🧠 Supported Models

The application currently supports the following models (configurable in `backend.py`):

| Provider | Model Name | Description |
| :--- | :--- | :--- |
| **Groq** | `llama-3.3-70b-versatile` | High performance, versatile open model. |
| **Groq** | `mixtral-8x7b-32768` | Strong reasoning capabilities. |
| **Groq** | `llama3-70b-8192` | (Backend only) Llama 3 70B. |
| **OpenAI** | `gpt-4o-mini` | Fast and cost-effective model from OpenAI. |

## 🤝 Contributing

Contributions are welcome! Please feel free to verify your changes by running the backend and frontend locally before submitting.

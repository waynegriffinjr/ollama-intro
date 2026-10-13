# Ollama Intro

A small Python demo that sends chat prompts to a locally running Ollama server. It
shows a basic question, then demonstrates retrieval-augmented generation (RAG)
style system prompts using a short FastAPI context.

## Prerequisites

- Python 3
- [Ollama](https://ollama.com/) installed and running
- The `llama3.2:1b` model downloaded in Ollama

## Setup

Start Ollama if it is not already running, then download the model:

```bash
ollama serve
ollama pull llama3.2:1b
```

In another terminal, from this folder, create and activate a virtual environment
and install the Python dependency:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

On Windows, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

## Run

```bash
python ollama_intro.py
```

The script checks the Ollama tags endpoint at `http://localhost:11434`, then
sends three non-streaming chat requests to the `llama3.2:1b` model. The final
two prompts use a sample FastAPI context to demonstrate answering from supplied
information and declining to answer outside that context.

## Configuration

The Ollama server URL and model are set near the top of
[`ollama_intro.py`](./ollama_intro.py) as `OLLAMA_URL` and `MODEL`.

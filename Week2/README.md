# MULTI-PROVIDER LLM ABSTRACTION (GEMINI & OLLAMA)

The objective of this experiment is to implement an abstract object-oriented interface for interacting with different LLM providers (cloud-hosted and locally hosted) through a unified client.

This design pattern decouples the application code from specific model APIs. Users can seamlessly choose between Google Gemini (cloud API) and Ollama (local open-source models such as LLaMA 3.2). A unit test suite using a mock provider is included to test client behavior without consuming API quota.

### Required files

- `.env` – stores the Gemini API key and provider configuration.
- `.gitignore` – excludes environment and cache files from Git tracking.
- `requirements.txt` – lists the required dependencies (`google-genai`, `requests`, `python-dotenv`, `pytest`).
- `llm_client.py` – defines the `LLMProvider` abstract base class, `GeminiProvider`, `OllamaProvider`, and `LLMClient`.
- `main.py` – interactive console interface to select a provider and submit questions.
- `test_client.py` – unit tests validating the `LLMClient` with a mock provider.

### Running the program

First, activate the virtual environment. Then install the required packages:

```bash
python -m pip install -r requirements.txt
```

Run the unit tests to verify client functionality:

```bash
python -m unittest test_client.py
```

Run the main application:

```bash
python main.py
```

Select your desired provider (`gemini` or `ollama`), enter your question, and view the model's response in the terminal.

# LLM OBSERVABILITY AND USAGE LOGGING WITH MONGODB

The objective of this experiment is to implement end-to-end observability, token usage tracking, and automated telemetry logging for LLM applications.

Monitoring production LLM applications requires tracking prompt token counts, candidate token counts, execution latency, estimated API costs, and failure rates. Every API invocation is automatically captured and persisted to a MongoDB collection for auditability and cost tracking.

### Required files

- `.env` – stores the Gemini API key, MongoDB connection URI, and token pricing rates.
- `.gitignore` – excludes sensitive credentials and virtual environment directories.
- `requirements.txt` – lists required packages (`google-genai`, `pymongo`, `requests`, `python-dotenv`, `pytest`).
- `llm_client.py` – defines `LLMResult`, providers, retry logic, cost calculation, and invocation tracking.
- `usage_logger.py` – manages the MongoDB connection and persists telemetry records with automatic retries.
- `main.py` – interactive script sending queries through the observable client.
- `test_client.py` – unit test ensuring token aggregation and logging record structure match expectations.

### Running the program

First, activate the virtual environment. Then install the required packages:

```bash
python -m pip install -r requirements.txt
```

Run the unit tests to verify client and logging records:

```bash
python -m unittest test_client.py
```

Run the main application:

```bash
python main.py
```

The script sends your prompt, outputs the generated response alongside token and latency metrics, and saves the complete telemetry record to MongoDB.

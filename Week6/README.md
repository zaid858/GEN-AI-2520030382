# LLM BASELINE EVALUATION (GOLDEN QUESTION SET - RELEASE V0.1)

The objective of this experiment is to establish an evaluation benchmark (Golden Question Set) for assessing the response accuracy and keyword coverage of an open-source Large Language Model (Llama 3.2 via Ollama).

The script evaluates the model against 30 curated questions on LLM concepts, tokenization, cost economics, and architecture. It computes automated keyword matching scores, classifies responses as `PASS` (≥ 60% coverage) or `REVIEW`, and exports the full evaluation report as a CSV file (`baseline_results.csv`) for Release v0.1.

### Required files

- `requirements.txt` – lists dependencies (`requests`).
- `golden_set.json` – contains the 30 benchmark questions, expected answers, key evaluation keywords, and documentation sources.
- `main.py` – queries the local Ollama Llama 3.2 model, evaluates keyword coverage, calculates baseline metrics, and exports `baseline_results.csv`.

### Running the program

First, ensure Ollama is running and the Llama 3.2 model is downloaded:

```bash
ollama --version
ollama pull llama3.2
```

Install the required Python package:

```bash
python -m pip install -r requirements.txt
```

Run the baseline evaluation:

```bash
python main.py
```

### Output

The program evaluates all 30 questions sequentially, displays the score and status for each, and generates:
- **`baseline_results.csv`** – complete question-by-question evaluation report.
- **Terminal Summary** – release version (`v0.1`), model name, pass/review counts, and average keyword coverage.

# TOKENIZER COMPARISON ACROSS LANGUAGES

The objective of this experiment is to analyze and compare how different tokenization algorithms (BPE, WordPiece, and SentencePiece) split text and represent tokens across different languages.

Tokenization efficiency significantly affects model context length, latency, and operational cost. This experiment tests three standard tokenizers:
1. **BPE (Byte-Pair Encoding)** via GPT-2
2. **WordPiece** via Multilingual BERT (`bert-base-multilingual-cased`)
3. **SentencePiece** via XLM-RoBERTa (`xlm-roberta-base`)

Each tokenizer processes identical sentences in **English**, **Telugu**, and **Hindi** to demonstrate vocabulary coverage, subword fragmentation, and non-Latin script token inflation.

### Required files

- `requirements.txt` – lists the required NLP packages (`transformers`, `sentencepiece`).
- `tokenizer_comparison.py` – loads all three tokenizers, runs the test sentences across English, Telugu, and Hindi, and prints the tokens, token IDs, and token counts.

### Running the program

First, activate the virtual environment. Then install the required packages:

```bash
python -m pip install -r requirements.txt
```

Run the comparison program:

```bash
python tokenizer_comparison.py
```

The program will display a side-by-side breakdown of token lists, token IDs, and total token counts for each language and algorithm.

# AUTOREGRESSIVE TEXT GENERATION – NEXT-WORD PREDICTION MODEL

The main objective of this experiment is to demonstrate the core mechanism of autoregressive text generation and next-token prediction in generative language models.

The program trains a simple bigram language model on a sample corpus by tokenizing text and constructing a word-to-word transition dictionary. It then generates new text autoregressively step-by-step by predicting the next word based on the current context and appending each generated token to feed into the subsequent prediction step.

The training corpus inside `autoregression.py` serves as the training data from which the vocabulary and next-word transition probabilities are learned. The `generate_text()` function initiates sequence generation from a seed word.

Before running the code, activate the virtual environment and install the required dependencies using:

**`python -m pip install -r requirements.txt`**

Then run the program using:

**`python autoregression.py`**

### The program:

1. Tokenizes the sample training corpus into lowercased words.
2. Builds a next-word transition model mapping each token to all observed successor tokens.
3. Takes an initial seed token (e.g., `"the"`) to begin autoregressive sequence generation.
4. Samples candidate next words iteratively, predicting one word at a time.
5. Feeds each newly predicted token back as the prompt context for the next generation step until reaching `max_words`.
6. Joins and displays the generated autoregressive text sequence in the terminal.

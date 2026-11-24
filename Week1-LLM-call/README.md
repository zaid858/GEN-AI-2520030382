# LLM_API_CALL USING PYTHON

The objective of this experiment is to connect a Python program to an AI model using an API key and get a response from the model.

For this experiment, we use the Gemini API. Its API key is stored in a `.env` file so that the key is kept separate from the program code. The `.gitignore` file is used to prevent sensitive or unnecessary files from being uploaded to GitHub. The script also implements retry logic with exponential backoff to handle temporary network or service unavailability.

### Required files

- `.env` – stores the Gemini API key.
- `.gitignore` – excludes files such as environment files from Git tracking.
- `requirements.txt` – lists the Python packages required for the experiment.
- `main.py` – contains the code to load the API key, create the Gemini client, send a prompt, and print the response.

### Running the program

First, activate the virtual environment. Then install the required packages:

```bash
python -m pip install -r requirements.txt
```

After adding the Gemini API key to the `.env` file, run the program:

```bash
python main.py
```

The program sends the prompt to Gemini through the API and displays the AI-generated response in the terminal.

# TOKEN ECONOMICS AND BUDGET PLANNING

The objective of this experiment is to model token economics, forecast operational costs, and perform capacity planning for LLM feature deployment.

Before launching an LLM-powered feature, engineering teams must calculate projected daily and monthly costs based on expected request volumes and token counts, while verifying whether peak traffic adheres to provider rate limits (RPM and TPM) and budget constraints.

### Required files

- `.env` – stores baseline assumptions such as daily requests, token counts, pricing per million tokens, rate limits, and budget thresholds.
- `requirements.txt` – lists the project dependencies (`python-dotenv`).
- `budget.py` – defines the `FeatureBudget` dataclass, cost calculations, safety margin buffers, and rate limit validation.
- `test_budget.py` – unit tests verifying cost estimation math, RPM limit checks, and budget compliance validation.

### Running the program

First, activate the virtual environment. Then install the required packages:

```bash
python -m pip install -r requirements.txt
```

Run the unit tests:

```bash
python -m unittest test_budget.py
```

Run the budget calculation program:

```bash
python budget.py
```

The program loads your deployment parameters from `.env`, prints a detailed financial projection (daily cost, monthly cost with safety buffer), and indicates whether rate limits (RPM, TPM) and budgets are satisfied.

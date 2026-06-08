# SWE-Agent ARVO Repair Eval


## Setup

1. Create and activate a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Configure your model and API key (this writes to mini-SWE-agent's global config,
   not this repo):
   ```bash
   mini-extra config setup
   ```
   You'll need an API key for whichever model you choose (e.g. `GEMINI_API_KEY` for
   Gemini models, Google AI Studio offers a free tier).

## Data

Currently using the existing ARVO database (`arvo.db`) for pipeline development and
validation. The final evaluation will use the newer dataset being rebuilt once it's ready.

`arvo.db` is too large to commit to the repo (~160MB). Download it with:
```bash
wget https://github.com/n132/ARVO-Meta/releases/download/v3.0.0/arvo.db
```

## Smoke test

Confirm your setup works end-to-end with the built-in hello-world example:
```bash
python -m minisweagent.run.hello_world -m gemini/gemini-2.5-flash --task "Create a file called test.txt with the text 'it works' inside it"
```

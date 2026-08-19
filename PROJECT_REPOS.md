# Setting Up GitHub Repos for Your Projects

You'll want one repo per project (dissertation pipeline, streaming pipeline, ELT pipeline, RAG system) — recruiters and the portfolio site both link out to these individually.

## 1. For each project, from its local folder:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/PROJECT_NAME.git
git push -u origin main
```

Create the empty repo on GitHub first (github.com → New repository → same name, public, no README) before running the `push`.

## 2. Add a `.gitignore` before your first commit

Don't commit credentials, virtual environments, or large data files. A minimal Python `.gitignore`:

```
__pycache__/
*.pyc
.env
.venv/
venv/
*.log
.DS_Store
node_modules/
*.egg-info/
.terraform/
*.tfstate
*.tfstate.backup
```

**Important:** if any project touched real API keys, cloud credentials, or `.env` files, check `git status` before your first commit to make sure none of those files are staged. If a secret was ever committed, rotating that key is safer than trying to scrub it from history.

## 3. README template for each project repo

This is what recruiters actually click into from your portfolio site — make it count.

```markdown
# Project Name

One-sentence description of what this does and why it exists.

## What it does
2-3 sentences: the problem, your approach, the outcome.

## Architecture
A simple diagram or bullet list of the data flow / system components.

## Tech stack
- Language/framework
- Key libraries
- Infrastructure (cloud, containers, CI/CD)

## Key results
Any numbers: performance, accuracy, latency, scale (records processed, F1 score, etc.)

## Running it locally
\`\`\`bash
# setup steps
\`\`\`

## What I'd improve next
1-2 honest notes on limitations or next steps — this signals engineering maturity more than pretending it's finished.
```

## 4. Once each repo is live, update your portfolio site

Go back to `index.html` in the portfolio folder, find the matching project card, and replace the `href="#"` placeholder with the real repo URL.

## Suggested repo names
- `knowledge-graph-pipeline` (dissertation)
- `market-data-streaming-pipeline`
- `cloud-native-elt-pipeline`
- `sec-filings-rag-system`

Keep these consistent with what you use in your résumé and LinkedIn Projects section so the trail is easy to follow.

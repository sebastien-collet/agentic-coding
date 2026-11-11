# Assistant Travel & Expense

Assistant conversationnel de consultation des politiques Travel & Expense. Il s'appuie sur le corpus Markdown de [`data/`](./data/) pour répondre aux questions en citant les sources.

## Pré-requis

- Python 3.11 ou plus récent
- [`uv`](https://docs.astral.sh/uv/)
- Un fournisseur et un modèle accessibles via l'API OpenAI ou un endpoint
  compatible

## Installer uv si nécessaire

Vérifie d'abord si `uv` est déjà disponible :

```bash
uv --version
```

Sinon, suis les instructions officielles adaptées à ton système dans le
[guide d'installation d'uv](https://docs.astral.sh/uv/getting-started/installation/).
Par exemple, sur macOS avec Homebrew :

```bash
brew install uv
```

Sur Windows avec `winget` :

```powershell
winget install --id astral-sh.uv -e
```

Sous Linux :
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Après l'installation, ouvre un nouveau terminal et vérifie avec `uv --version`.

## Installation

Depuis la racine du dépôt :

```bash
uv sync --locked
cp .env.example .env
```

Configure les variables nécessaires à ton fournisseur. Ne partage pas et ne
committe pas le fichier `.env`. Le fait qu'il soit ignoré par Git ne le rend pas
invisible à Copilot Agent : utilise une clé temporaire à faible quota, et ne
colle jamais de secret dans le chat, le code ou les consignes. Pour empêcher
réellement l'agent d'accéder à une clé, celle-ci doit rester dans un service
séparé auquel l'application fait appel ; une variable d'environnement
accessible au processus de l'agent n'est pas isolée.

Vérifie l'environnement :

```bash
uv run python -c "import langgraph, streamlit; print('Environnement prêt')"
```

L'application nécessite une clé d'API et un nom de modèle configurés dans
`.env`.

# Getting Started

This guide walks you through setting up the MkDocs POC project locally.

## Prerequisites

- **Python 3.8+**
- **pip** (Python package manager)

## Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-org/mkdocs-poc.git
cd mkdocs-poc
```

### Step 2: Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

## Running Locally

Start the development server:

```bash
mkdocs serve
```

Then open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser. The site will auto-reload when you edit the documentation.

## Building the Site

To build static files without serving:

```bash
mkdocs build
```

Output is written to the `site/` directory.

## Project Structure

```
mkdocs-poc/
├── docs/               # Documentation source (Markdown)
│   ├── index.md
│   ├── getting-started.md
│   ├── code-examples.md
│   └── accessibility.md
├── mkdocs.yml          # MkDocs configuration
├── requirements.txt    # Python dependencies
└── .github/
    └── workflows/
        └── deploy.yml  # CI/CD pipeline
```

## Next Steps

- [Code Examples](code-examples.md) — See Java, YAML, and Bash snippets
- [Accessibility](accessibility.md) — Accessibility configuration

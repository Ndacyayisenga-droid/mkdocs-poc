# MkDocs POC - Documentation Requirements Evaluation

A Proof of Concept (POC) MkDocs documentation site demonstrating documentation requirements and deployable via CI/CD.

## Features Demonstrated

| Requirement | Implementation |
|-------------|----------------|
| Docs-as-Code (Markdown) | All content in `docs/*.md` |
| Syntax highlighting | Material theme + PyMdown Extensions |
| Line numbers | `pymdownx.highlight` with `linenums: true` |
| Copy-to-clipboard | Material theme `content.code.copy` |
| Search | Material built-in search |
| PDF export | `mkdocs-with-pdf` plugin |
| TOC with linkable subheaders | `toc.permalink: true` |
| Responsive design | Material theme (mobile/desktop) |
| Accessibility | Semantic HTML, keyboard nav, theme toggle |
| Dead link detection | `mkdocs-linkcheck` in CI |
| Mermaid diagrams | PyMdown SuperFences |
| Dark/light theme | Material palette toggle |
| Code tabs | PyMdown Tabbed extension |

## Quick Start

### Prerequisites

- Python 3.8+
- pip

### Run Locally

```bash
pip install -r requirements.txt
mkdocs serve
```

Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

### Build Docs

```bash
mkdocs build
```

Output is written to `site/`.

## Generate PDF

PDF generation uses the `mkdocs-with-pdf` plugin with WeasyPrint. It requires extra dependencies.

### Step 1: Install PDF dependencies

```bash
pip install -r requirements-pdf.txt
```

### Step 2: Install system libraries (WeasyPrint)

- **macOS**: `brew install cairo pango gdk-pixbuf libffi`
- **Ubuntu/Debian**: `sudo apt-get install libpango-1.0-0 libpangocairo-1.0-0 libgdk-pixbuf2.0-0 libffi-dev shared-mime-info`
- **Windows**: See [WeasyPrint installation](https://doc.courtbouillon.org/weasyprint/stable/first_steps.html#windows)

### Step 3: Build with PDF

```bash
mkdocs build -f mkdocs-pdf.yml
```

The PDF is written to `site/pdf/documentation.pdf`.

## CI/CD Pipeline

The GitHub Actions workflow (`.github/workflows/deploy.yml`):

1. **Checkout** — Fetches the repository
2. **Setup Python** — Python 3.11
3. **Install dependencies** — `pip install -r requirements.txt`
4. **Build** — `mkdocs build --strict`
5. **Link check** — Lychee on built `site/` (dead link detection)
6. **Deploy** — Pushes `site/` to GitHub Pages

### Deploying to GitHub Pages

1. In the repo: **Settings → Pages**
2. Set source to **GitHub Actions**
3. Push to `main` or `master` to trigger deploy

### Dead Link Detection

- **CI**: Lychee checks the built site (`site/`) for broken links. The workflow fails if broken links are found.
- **Local**: Use `mkdocs-linkcheck docs --recurse` to check Markdown files before pushing.
- **Test link**: The home page includes an intentionally broken link for testing. It is excluded in `.lycheeignore` so CI passes. Remove the exclusion to verify detection.

## Project Structure

```
mkdocs-poc/
├── docs/
│   ├── index.md
│   ├── getting-started.md
│   ├── code-examples.md
│   └── accessibility.md
├── mkdocs.yml
├── mkdocs-pdf.yml       # Config for PDF export
├── requirements.txt
├── requirements-pdf.txt # Optional: for PDF export
├── .lycheeignore        # Link check exclusions
├── .github/workflows/deploy.yml
└── README.md
```

## Optional: AsciiDoc Support

For AsciiDoc support, you can use `mkdocs-asciidoctor-backend` (beta):

```bash
pip install mkdocs-asciidoctor-backend
```

Then configure it in `mkdocs.yml` and add `.adoc` files. Note: this replaces the default Markdown backend; mixed Markdown/AsciiDoc has limited support.

## License

MIT

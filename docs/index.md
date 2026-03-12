# MkDocs POC Documentation

Welcome to the **MkDocs Proof of Concept** documentation site. This POC demonstrates how MkDocs with the Material theme satisfies common documentation requirements.

## Overview

This documentation is built with **Docs-as-Code** using Markdown. All content is version-controlled and built via CI/CD.

### Key Features Demonstrated

- **Docs-as-Code** — Markdown files in `docs/`
- **Syntax highlighting** — Code blocks with language-specific coloring
- **Line numbers** — Optional line numbering in code snippets
- **Copy button** — One-click copy for code blocks
- **Search** — Built-in full-text search (use the search bar above)
- **PDF export** — Generate a single PDF from all pages
- **Table of Contents** — Auto-generated TOC with linkable headers
- **Responsive design** — Works on mobile and desktop
- **Accessibility** — Semantic HTML, keyboard navigation, theme support

## Quick Links

| Page | Description |
|------|-------------|
| [Getting Started](getting-started.md) | Installation and local development |
| [Code Examples](code-examples.md) | Java, YAML, Bash examples and Mermaid diagrams |
| [Accessibility](accessibility.md) | Accessibility configuration and tips |

## Architecture

The following diagram shows the documentation build pipeline:

``` mermaid
flowchart LR
    subgraph Source
        MD[Markdown Files]
        YAML[mkdocs.yml]
    end
    
    subgraph Build
        MkDocs[MkDocs Build]
        PDF[PDF Export]
    end
    
    subgraph Output
        HTML[Static HTML Site]
        Site[GitHub Pages]
    end
    
    MD --> MkDocs
    YAML --> MkDocs
    MkDocs --> HTML
    MkDocs --> PDF
    HTML --> Site
```

## Getting Help

- Internal link: [Code Examples — Java](code-examples.md#java-example)
- External link: [MkDocs Documentation](https://www.mkdocs.org/)
- External link: [Python Documentation](https://docs.python.org/3/)
- Intentionally broken link (for testing dead link detection): [Broken Example](https://httpbin.org/status/404)

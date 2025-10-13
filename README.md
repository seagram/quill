<div align="center">
  <img src="./assets/quill.svg" alt="Quill Logo" width="200">
  <h1>Quill</h1>
  A fast, modern toolchain for writing screenplays.
  <p>
    <a href="#about">About</a> •
    <a href="#tools">Tools</a> •
    <a href="#status">Status</a> •
    <a href="#acknowledgements">Acknowledgements</a>
  </p>
</div>

## About

Quill is a modern toolkit for Fountain-based screenplay workflows.

> **What is Fountain?**
>
> [Fountain](https://fountain.io) is a markup language for writing screenplays in plain text.
> It's open source, human-readable, and version-control-friendly.

## Tools

Quill provides the following command-line tools:

### Init

Create a new Fountain screenplay with a starter template including title page, scene headings, and section structure.

```bash
# Create screenplay with default template
quill init

# Interactive mode - prompts for title page information
quill init -i
```

### Parser

Parse Fountain files into an abstract syntax tree (AST) for screenplay analysis.

```bash
# Human-readable tree view (default)
quill parse script.fountain

# JSON output
quill parse script.fountain --format json

# Compact JSON (no whitespace)
quill parse script.fountain --format compact
```

### Linter

Detect formatting issues and styling errors that differ from conventional Fountain syntax.

```bash
quill lint script.fountain
```

### Formatter

Automatically format your Fountain files to the standard Fountain specification.

```bash
quill format script.fountain
```

### Export

Convert Fountain screenplays to PDF or Final Draft format.

```bash
quill export script.fountain --format pdf
quill export script.fountain --format fdx
```

### Live Preview

View your screenplay in a browser with real-time updates as you edit.

```bash
quill preview script.fountain
```

### LSP Server

Language Server Protocol implementation for real-time diagnostics, formatting, and editor integration.

```bash
quill server
```

### Stats

Generate a detailed report about your screenplay.

```bash
quill stats script.fountain
```

**Statistics include:**

- Page count and estimated runtime
- Scene breakdown (count, average length, location distribution)
- Dialogue distribution per character
- Action vs. dialogue ratio
- Character appearances and scene presence
- Scene transitions analysis
- Day/night scene ratio
- Interior/exterior location breakdown

## Status

Quill is in a pre-alpha stage and is currently under active development.

## Acknowledgements

Thank you to John August, Nima Yousefi, and Stu Maschwitz for creating the Fountain specification and pioneering open-source software in the screenwriting industry.

---

**Note:** Quill is not in any way affiliated with or endorsed by the Fountain project.

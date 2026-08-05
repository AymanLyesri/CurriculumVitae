# 📄 Curriculum Vitae (LaTeX)

My CV is written entirely in **LaTeX** and is automatically built and published using **GitHub Actions**.

Every push to the repository generates fresh PDF versions of the CV (English and French), fetches the latest GitHub star count for ArchEclipse, and publishes the PDFs as downloadable release assets.

---

## ✨ Features

- 🌍 English and French versions from a single source
- ⭐ Automatically embeds the latest GitHub star count
- 🤖 Fully automated builds with GitHub Actions
- 📦 PDFs attached to every GitHub Release
- 🚀 No manual compilation required

---

## Repository Structure

```
.
├── .github/
│   └── workflows/
│       └── build.yml
├── CV-AYMAN-LYESRI.tex
├── stars.tex
└── README.md
```

---

## GitHub Action

The workflow automatically:

1. Checks out the repository.
2. Fetches the latest GitHub star count from the ArchEclipse repository.
3. Generates `stars.tex`.
4. Builds the English and French PDFs using LaTeX.
5. Creates or updates a GitHub Release.
6. Uploads both PDFs as release assets.

The workflow runs on:

- Every push to `main` or `master`
- Manual execution via **workflow_dispatch**

---

## Building Locally

### Requirements

- TeX Live (recommended)
- latexmk

### Compile

```bash
latexmk -pdf CV-AYMAN-LYESRI.tex
```

or

```bash
pdflatex CV-AYMAN-LYESRI.tex
```

---

## Automatic GitHub Stars

The workflow generates:

```tex
\renewcommand{\archEclipseStars}{534}
```

which is included automatically by:

```latex
\InputIfFileExists{stars.tex}{}{}
```

If the workflow hasn't generated it yet, the document falls back to:

```latex
\providecommand{\archEclipseStars}{500}
```

---

## Releases

Each workflow execution publishes:

- 🇬🇧 `CV-AYMAN-LYESRI-EN.pdf`
- 🇫🇷 `CV-AYMAN-LYESRI-FR.pdf`

making the latest version always available from the repository's Releases page.

---

## License

This repository contains my personal résumé.

Feel free to use the GitHub Actions workflow or LaTeX structure as inspiration, but please do not redistribute the contents of the CV itself.

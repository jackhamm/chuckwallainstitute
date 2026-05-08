# Chuck Walla Institute of Advanced Physics

A mock-academic static site, built with [Quarto](https://quarto.org).

## Local development

Prerequisites: Quarto (`brew install quarto` or see quarto.org), Python 3.10+,
and a few packages for executing post code blocks:

```bash
pip install numpy matplotlib jupyter
```

Preview the site with live reload:

```bash
quarto preview
```

Render to `_site/`:

```bash
quarto render
```

## Authoring posts

Posts live under `posts/<slug>/index.qmd`. A minimal post:

```yaml
---
title: "..."
description: "..."
author:
  - name: "..."
date: "2026-05-08"
categories: [QED, ...]
---
```

Math: `$inline$` and `$$display$$`. Numbered, referenceable equations:

```markdown
$$ E = mc^2 $$ {#eq-einstein}

As shown in @eq-einstein ...
```

Computed figures: a `{python}` (or `{r}`, `{julia}`) chunk with `#| label: fig-foo`
and `#| fig-cap: "..."` is rendered at build time and citable as `@fig-foo`.

## Deployment

Push to `main`; the GitHub Action in `.github/workflows/publish.yml` renders
and deploys to GitHub Pages. Enable Pages in repo settings → "GitHub Actions" source.

## Structure

```
_quarto.yml           # site config
styles.scss           # desert theme
index.qmd             # landing
posts.qmd             # listing page
posts/<slug>/index.qmd
references.bib
assets/crest.svg
```

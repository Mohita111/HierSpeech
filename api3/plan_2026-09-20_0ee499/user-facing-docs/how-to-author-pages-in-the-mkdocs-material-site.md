# How to Author Pages in the MkDocs Material Site

This guide explains how to add a new Markdown guide to the DigitalOcean Solutions Docs site, register it in navigation, and use the available styling features so the page appears correctly and looks consistent with existing guides.

## Overview

The site is built with MkDocs Material. The content you write is plain Markdown. When you add a page and register it in the site configuration, MkDocs automatically applies the site theme, navigation, search, and code formatting.

## 1. Create a New Markdown Page

Documentation pages live in the `DigitalOcean-Docs/docs/` folder.

To add a new guide:

1. Create a new `.md` file in `DigitalOcean-Docs/docs/`.
2. Give the file a clear name. For example: `My New Guide.md`.
3. Start the page with YAML front matter. Existing catalog pages use a consistent front matter block.

Example front matter for a new guide:

```yaml
---
title: My New Guide
description: A short summary of what this guide covers.
product: Marketplace
url: https://docs.digitalocean.com/products/marketplace/catalog/my-new-guide/
last_updated: "2026-06-11"
---
```

The `last_updated` value is a date string and should be wrapped in quotes.

After the front matter, add a level-one heading that matches the page title:

```markdown
# My New Guide
```

Then write the page content using normal Markdown.

## 2. Register the Page in Navigation

The navigation is defined in `DigitalOcean-Docs/mkdocs.yml`.

Locate the `nav` section. Existing navigation has a top-level `Welcome` item and a `Core Integrations` section. Add your new guide under `Core Integrations`.

Example:

```yaml
nav:
  - Welcome: index.md
  - Core Integrations:
      - Bitwarden Deployment: Bitwarden.md
      - Storage with CSI for S3: CSI for S3.md
      - Observability via OpenLIT: OpenLIT.md
      - Database Cluster with Pangolin (CE): Pangolin (CE).md
      - My New Guide: My New Guide.md
```

The label on the left is the text shown in navigation. The value on the right is the file name in the `docs` folder.

## 3. Link from the Home Page

The home page, `DigitalOcean-Docs/docs/index.md`, contains a list of available deployments grouped by category. To make your new guide easy to find, add a bullet link in the appropriate category.

For example:

```markdown
### 🔐 Security & Identity
* **[Bitwarden Deployment](Bitwarden.md)**  
  Step-by-step blueprint for self-hosting a secure password management vault backed by cloud block storage.
* **[My New Guide](My New Guide.md)**  
  A short description of what the new guide covers.
```

## 4. Front Matter Conventions

Existing catalog pages use these fields:

| Field | Purpose |
|---|---|
| `title` | The display title for the page |
| `description` | A one-sentence summary of the page |
| `product` | The related product or catalog category, such as `Marketplace` |
| `url` | The canonical DigitalOcean documentation URL for the original page |
| `last_updated` | The date the page was generated or last updated, in `YYYY-MM-DD` format |

Keeping these fields consistent helps the site display pages uniformly and makes future maintenance easier.

## 5. Markdown Extensions You Can Use

The site has several Markdown extensions enabled. These are already configured, so you can use their syntax directly.

### Admonitions

You can create callouts such as notes, warnings, and tips.

Example:

```markdown
!!! note
    This is an informational note.
```

You can replace `note` with `warning`, `tip`, `danger`, `info`, or other supported admonition types.

### Collapsible Details

Because detail blocks are enabled, you can create collapsible callout sections.

Example:

```markdown
??? note "Click to expand"
    This content is hidden until the user expands the section.
```

### Fenced Code Blocks

Use triple backticks with a language identifier for syntax-highlighted code blocks.

Example:

````markdown
```shell
curl -X POST https://api.digitalocean.com/v2/droplets
```
````

The `shell` language identifier enables shell syntax highlighting. You can also use other languages such as `python`, `javascript`, `yaml`, or `json`.

### Superfences

The `pymdownx.superfences` extension allows more complex code blocks, including nested fences and code blocks inside admonitions. This lets you place code examples inside callouts without breaking the page rendering.

### Highlighted Code with Anchor Line Numbers

The highlight extension is configured with anchor line numbers enabled. This means highlighted code blocks can expose line number anchors for easier referencing and linking to specific lines of code.

Pygments language classes are also enabled, helping code blocks receive appropriate styling based on the language.

## 6. Theme Features

The site theme includes several built-in features that affect how your pages appear.

### Navigation Tabs

Top-level navigation sections appear as tabs across the top of the site. Since `Core Integrations` is a top-level section, its pages appear under that tab.

### Code Copy Buttons

Every code block includes a built-in copy button. Users can click the button to copy the code content to their clipboard. You do not need to add anything to enable this.

### Search Suggestions

As users type in the search bar, the site shows suggested results automatically.

### Search Highlighting

Search matches are highlighted in the search results, making it easier for users to find terms in the documentation.

## 7. Light and Dark Mode

The site supports both light and dark color schemes. It automatically follows the visitor’s operating system color preferences.

- Light mode uses the `default` scheme with blue primary and accent colors.
- Dark mode uses the `slate` scheme with blue primary and accent colors.

A toggle icon in the theme lets users manually switch between light and dark mode.

You do not need to add any page-level configuration to support this. The palette applies automatically across all pages.

## 8. Final Styling Checklist

After adding and registering a page, check that:

- The page appears in the correct navigation section under **Core Integrations**.
- The title matches the first heading on the page.
- Front matter includes `title`, `description`, `product`, `url`, and `last_updated`.
- Code blocks show syntax highlighting and a copy button.
- Admonitions and collapsible sections render correctly.
- The page looks correct in both light and dark mode.
- The home page link is included if you want the guide listed from the catalog start page.

Following these conventions keeps new guides visually and structurally consistent with the existing DigitalOcean Solutions Docs site.
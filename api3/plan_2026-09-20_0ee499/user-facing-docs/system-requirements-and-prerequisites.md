# System Requirements and Prerequisites

This guide explains everything you need to prepare before you can run or build either of the documentation sites in this repository.  
There are two separate sites, each with its own set of requirements:

- **Docusaurus website** — a modern static site for general web content
- **DigitalOcean Solutions Docs** — a documentation site built with MkDocs and the Material theme

Use the sections below to check that your computer is ready to work with both sites.

---

## 1. Node.js (for the Docusaurus website)

The Docusaurus-based website requires **Node.js version 20 or newer**.

**How to check your version:**

Open a terminal and run:

```bash
node --version
```

If the output shows `v20.x` or later, you are ready.  
If you see an older version or the command is not recognized, install the latest Node.js 20+ release from the official Node.js website.

> **Why it matters:** The website uses tools that depend on modern JavaScript features available only in Node.js 20 and above.

---

## 2. Python and MkDocs (for the DigitalOcean Solutions Docs site)

The DigitalOcean Solutions Docs site runs on Python and MkDocs.

### Python version

You need **Python 3.12 or newer**.

Check your Python version with:

```bash
python3 --version
```

or, on some systems:

```bash
python --version
```

The output should show `Python 3.12.x` or later.

### Required Python packages

The documentation site also needs two Python packages installed:

- **MkDocs** version 1.5.0 or newer
- **MkDocs Material** version 9.0.0 or newer

If you are setting up a new environment, install them with:

```bash
pip install "mkdocs>=1.5.0" "mkdocs-material>=9.0.0"
```

After installation, you can verify MkDocs is available with:

```bash
mkdocs --version
```

---

## 3. Package managers

Package managers are tools that install and manage the libraries your documentation sites depend on. You need separate package managers for the two sites.

### For the Docusaurus website

You can use **Yarn** or **npm**. The project instructions in this repository recommend Yarn.

Check which one you have:

```bash
yarn --version
```

or

```bash
npm --version
```

Either command should return a version number. If Yarn is not installed, you can install it from the Yarn website, or use npm, which ships with Node.js.

### For the DigitalOcean Solutions Docs site

Use **pip**, which is Python’s standard package installer.

Verify pip with:

```bash
pip --version
```

This command should return a version number. If pip is missing, reinstall or update Python, as pip is included with modern Python distributions.

---

## 4. Git and GitHub account (for deployment to GitHub Pages)

Both documentation sites can be deployed to GitHub Pages, which requires Git and a GitHub account.

### Git

Git is a version-control tool used to track changes and push your site to GitHub.

Check that Git is installed:

```bash
git --version
```

You should see a version number such as `git version 2.x.x`.  
If Git is not installed, download it from the official Git website.

### GitHub account

You need a **GitHub account** to:

- Store the repository online
- Publish the site to GitHub Pages
- Authenticate deployment actions

During deployment of the Docusaurus site, you will be asked for your GitHub username. Make sure you are logged in to GitHub on your computer, or have your username and access token ready.

---

## 5. Recommended editor tooling for Markdown and MDX authoring

You do not need a special editor to contribute documentation, but using an editor with good Markdown and MDX support makes the work easier.

Recommended setup:

- **Visual Studio Code** — a free, cross-platform editor
- A **Markdown preview** extension so you can see formatted text while you type
- A **YAML support** extension for editing navigation and configuration files
- Syntax highlighting for **MDX** if you plan to edit the Docusaurus website

Any editor that can preview Markdown and handle YAML files will work. The key is to see your changes before you build the site.

---

## Quick readiness checklist

| Requirement | Minimum version | How to verify |
|-------------|----------------|----------------|
| Node.js | 20 or newer | `node --version` |
| Yarn or npm | Any recent version | `yarn --version` or `npm --version` |
| Python | 3.12 or newer | `python3 --version` |
| pip | Any recent version | `pip --version` |
| MkDocs | 1.5.0 or newer | `mkdocs --version` |
| MkDocs Material | 9.0.0 or newer | Install with pip and check `mkdocs --version` |
| Git | Any recent version | `git --version` |
| GitHub account |Active | Sign in at github.com |

If you can check off every item in the table, your machine is ready to build and run both documentation sites locally.
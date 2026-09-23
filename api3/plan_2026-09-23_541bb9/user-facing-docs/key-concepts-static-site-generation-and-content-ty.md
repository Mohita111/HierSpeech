# Key Concepts: Static Site Generation and Content Types

This guide explains the core ideas behind how Docusaurus works. By the end, you will understand why Docusaurus sites are fast, how your content is organized, and what happens when you build or publish your site.

---

## 1. What Is a Static Site Generator?

A **static site generator** is a tool that takes your content — like text, images, and formatting — and turns it into a complete website made of simple, ready-to-serve files.

Think of it like a printing press for websites:

- You write your content once, in easy-to-read plain text files.
- The generator "prints" a finished set of pages.
- Every visitor gets the same ready-made page — no waiting for the site to assemble itself on the fly.

This is different from older, dynamic websites, where each page is assembled from scratch every time someone visits. A static site is prepared ahead of time, which makes it much faster and more reliable.

### Key Benefits

- **Speed** — Pages load almost instantly because there is nothing to build at the moment of the visit.
- **Reliability** — With no behind-the-scenes assembly required, there are fewer things that can go wrong.
- **Simplicity** — The final result is just a folder of files that can be hosted almost anywhere.
- **Security** — With no live processing of visitor requests, there is a smaller surface for attacks.

Docusaurus is a static site generator designed specifically for documentation websites, blogs, and project sites.

---

## 2. How Docusaurus Pre-Renders Pages

Docusaurus uses a popular tool called **React** to define how pages look and behave. React normally runs in the visitor's web browser, assembling the page after it has been downloaded.

Docusaurus changes this model in an important way: it **pre-renders** the pages ahead of time.

### What Pre-Rendering Means

When you build your Docusaurus site, the system:

1. Takes every page of your site.
2. Runs the page through React once — on your computer or a build server, not in the visitor's browser.
3. Saves the completed result as a plain, static page.

When a visitor arrives, the browser downloads the finished page immediately. The browser does not need to do any assembly work to show the content. This is why the first thing a visitor sees appears so quickly.

### Interactive Parts Still Work

Even though pages are pre-rendered, they are not frozen or lifeless. Interactive elements — such as search boxes, navigation menus, and dark-mode toggles — become active after the initial page loads. Docusaurus adds that interactivity back in the background, giving you the best of both worlds:

- **Instant content** — The page appears immediately.
- **Full interactivity** — Features respond the moment the visitor is ready to use them.

This approach is a large part of why Docusaurus sites feel fast without sacrificing modern, dynamic behavior.

---

## 3. Content Types

Docusaurus organizes content into distinct types. Each type has its own purpose, its own layout conventions, and its own way of presenting information.

### Documentation

**Documentation** is the heart of most Docusaurus projects. It is designed for structured, long-form guides and reference material.

Documentation content is organized in a **hierarchy**, meaning it is grouped into sections and subsections. This hierarchy becomes a sidebar navigation menu, allowing readers to move through related topics in a logical order.

Documentation is ideal for:

- Getting-started guides
- Step-by-step tutorials
- Reference material
- Frequently asked questions
- Concept explainers like this one

### Blog Posts

**Blog posts** are time-based content — announcements, release notes, updates, and articles organized by date.

The blog section automatically manages chronological ordering. Recent posts appear first, and readers can browse an archive of older entries. Blog posts also support features like:

- Author attribution
- Publication dates
- Tags and categories
- Reading-time estimates

A blog is perfect for company updates, product announcements, and regularly published articles.

### Standalone Pages

**Standalone pages** are one-off pages that do not belong to a documentation hierarchy or a chronological blog feed.

A standalone page typically has its own layout and serves a single, focused purpose. Common examples include:

- A landing page
- A "Contact Us" page
- A feature showcase
- A pricing page
- A custom-designed homepage

Standalone pages give you the freedom to design a page that looks and feels exactly the way you want, without fitting into the documentation or blog structures.

### How the Three Types Work Together

A complete Docusaurus site often combines all three:

- The **documentation** section holds the durable, reference material.
- The **blog** shares news and updates over time.
- **Standalone pages** present the public-facing front of the project.

Together, they cover the full range of what a project site needs.

---

## 4. Markdown and MDX Support

Docusaurus lets you write most of your content in **Markdown** — a lightweight, plain-text formatting language that is easy to learn and read even before it is converted to a website.

### What Markdown Does

Markdown uses simple symbols to indicate formatting. For example:

- A heading is marked with a `#` symbol at the start of a line.
- A bullet list uses `-` or `*` at the start of a line.
- Bold text is wrapped in double asterisks like `**this**`.
- A link is written as `[link text](destination)`.

Because Markdown is plain text, your source content remains readable and easy to edit, even outside of any special tool.

### MDX: Markdown Plus Interactive Components

Docusaurus also supports **MDX**, which extends Markdown with the ability to include interactive elements directly inside your content.

With MDX, you are not limited to static text and images. You can embed:

- Tabs that let readers switch between different views
- Alert boxes that highlight warnings or tips
- Custom interactive widgets
- Dynamic content that changes based on visitor interaction

MDX gives you the simplicity of Markdown with the power of a full interactive page, all in a single file.

### Why This Matters

The combination of Markdown and MDX means:

- Writing content is fast and approachable — even for non-technical contributors.
- The source text stays clean and readable.
- You can drop in rich, interactive features wherever they add value.

---

## 5. Build Time vs. Runtime

One of the most important ideas to understand about Docusaurus is the distinction between **build time** and **runtime**.

### Build Time

**Build time** is the moment when you run the command to generate your finished website. During build time, Docusaurus:

- Reads all of your Markdown and MDX content.
- Converts it into formatted, styled pages.
- Pre-renders every page into its final static form.
- Organizes everything into a complete, deployable site.

Build time happens on your own computer or on a build server. It happens once, before any visitor ever sees the site.

### Runtime

**Runtime** is the moment a visitor opens your site in their web browser. During runtime:

- The browser downloads the already-built page.
- The visitor immediately sees the content.
- Interactive features become active.
- Navigation between pages happens without a full rebuild.

Nothing about the site's content is assembled from scratch during runtime. The heavy lifting was already done at build time.

### Why This Distinction Matters

The build-time/runtime split is the foundation of Docusaurus performance:

| | Build Time | Runtime |
|---|---|---|
| **When** | Before publishing | When a visitor opens the site |
| **Where** | Your computer or a build server | The visitor's browser |
| **What happens** | Pages are assembled, formatted, and saved | Pages are displayed and become interactive |
| **Frequency** | Once per update | Every visit |

Because all the assembly work is done once at build time, it is never repeated for individual visitors. Every visitor benefits from work done ahead of time, which is why each visit feels immediate and effortless.

---

## Summary

Docusaurus is built on a simple but powerful set of ideas:

1. **It is a static site generator** — your content becomes ready-made pages before anyone visits.
2. **It pre-renders pages** — the visible content is prepared ahead of time, not assembled in the visitor's browser.
3. **It organizes content into types** — documentation for structured guides, blog posts for time-based updates, and standalone pages for one-off designs.
4. **It supports Markdown and MDX** — plain-text writing with the option to add interactive elements.
5. **It separates build time from runtime** — all the hard work happens once, so every visit is fast.

Together, these concepts explain why Docusaurus sites are quick, easy to maintain, and flexible enough to serve documentation, blogs, and custom pages — all from a single system.
# Key Concepts: Static Site Generators and Content Types

Welcome! This guide explains how this documentation platform works behind the scenes. Whether you're reading the docs or writing your own, you'll understand where content lives, how it's organized, and what happens when it gets published.

## What Is a Static Site Generator?

A static site generator takes your written content—pages, guides, and blog posts—and turns it into a complete website before anyone visits. Instead of building each page on the spot, every page is prepared in advance as a finished file that web browsers can display instantly.

Imagine writing a book manuscript. The generator is the printing press: it takes all your chapters, applies the design and formatting, and produces the final bound book. Visitors receive the printed pages, not your raw drafts.

This approach makes websites fast, reliable, and easy to host anywhere.

## Two Ways to Build Documentation

This project includes two popular documentation generators, each with its own strengths.

### Docusaurus

Docusaurus is an all-in-one platform that gives you a documentation section, a blog, and standard website pages—all under one roof. It comes with a ready-made navigation bar, a footer, light and dark color modes, and support for search.

**Best for:** Projects that need both reference documentation and regular blog updates, along with a polished site layout.

### MkDocs Material

MkDocs with the Material theme focuses on clean, no-fuss documentation. You list your pages in one master navigation map, and the site builds exactly that structure. It includes a search bar with suggestions, a light/dark toggle, and built-in formatting for code samples and callout boxes.

**Best for:** Documentation-only sites where simplicity and speed matter most.

### Key Differences at a Glance

| Feature | Docusaurus | MkDocs Material |
|---|---|---|
| Documentation pages | Yes | Yes |
| Blog | Yes (built-in) | Not included |
| Custom website pages | Yes | Limited |
| Navigation setup | Automatic sidebar or manual list | Single navigation map |
| Light/dark mode | Yes | Yes (with toggle) |
| Search | Via plugins | Built-in with suggestions and highlighting |
| Code sample styling | Multiple theme options | Built-in with line numbers |

## Types of Content in Docusaurus

A Docusaurus site organizes content into three distinct areas.

### 1. Documentation Pages

Your reference material lives in a dedicated documentation area. Each page is written using simple text formatting. You can create folders to group related pages, and the site automatically generates a navigation sidebar that mirrors your folder structure.

For example, a "Tutorial" section might contain pages like "Create a Document" or "Deploy Your Site," each accessible from a left-hand sidebar with previous/next buttons for step-by-step reading.

### 2. Blog Posts

Blog posts are separate from documentation. They are dated entries—the date is part of the file name, such as `2021-08-26-welcome`. Each post includes:

- **A title** visible at the top of the page and in listings
- **Authors** credited as the contributors
- **Tags** that categorize the post by topic
- **A short summary** shown in list views, with the rest of the article hidden until the reader clicks "read more"

Blog posts can also include images stored alongside the post content. The system tracks reading time and produces RSS and Atom feeds so readers can subscribe.

### 3. Standard Website Pages

Besides documentation and blog content, you can have regular website pages—such as a landing page, an about page, or a contact page. These provide more layout flexibility than documentation pages and can be fully customized.

## How Content Gets Organized

### Sidebars in Docusaurus

A sidebar is the navigation menu that appears next to your documentation. In this setup, the sidebar is generated automatically from the documentation folder structure. Whatever sections and pages you create appear in the sidebar in the same order.

You also have the option to define a sidebar manually—listing each page by name and grouping them into labeled categories. This gives you complete control over the order and grouping, independent of how files are stored.

### Navigation in MkDocs

MkDocs takes a different approach. Instead of an auto-generated sidebar, you maintain a single navigation map that explicitly lists each section and the exact page that belongs to it.

This project's navigation map, for example, includes:

- **Welcome** — the landing page for the documentation
- **Core Integrations** — a section grouping four pages:
  - Bitwarden Deployment
  - Storage with CSI for S3
  - Observability via OpenLIT
  - Database Cluster with Pangolin (CE)

Each entry in the map points to a specific content file. The file's contents become the page at that spot in the navigation. Reordering the site is as simple as changing the order in the map.

## Metadata: Front Matter, Tags, and Authors

### Front Matter

Every documentation page and blog post can begin with a hidden block of metadata called *front matter*. This contains information that isn't displayed as part of the page body but controls how the page behaves and appears. Common front matter fields include:

- **`title`** — the page's display name
- **`slug`** — the end of the page's web address
- **`authors`** — who wrote the content
- **`tags`** — topic labels for grouping

### Tags

Tags are short topic labels attached to blog posts. A single post can carry multiple tags—for example, `facebook`, `hello`, and `docusaurus`. Readers can click a tag to see all posts sharing that label, making related content easier to discover.

The system can be configured to warn if tags are entered directly on a post rather than managed in a central list, encouraging consistency across the site.

### Authors

Authors are named contributors credited for a post. Blog posts list one or more authors, and the system supports a shared author list where you define names, bios, and profile pictures once. Like tags, the system can warn if authors are referenced inline rather than from the central list, helping maintain a unified author directory.

## How MkDocs Navigation Maps to Site Structure

In MkDocs, the navigation map is the single source of truth for your site's structure. Each line in the map represents one page or one section. The left-hand navigation menu that visitors see is built directly from this list—nothing appears in the menu unless it's listed here.

The mapping is one-to-one:

- A top-level entry appears as a main menu item
- A nested entry appears under a collapsible section
- Pages appear in exactly the order they're listed

This explicit approach means you always know exactly where each page will appear in the final site.

## From Source Content to Published Website

All content starts as human-readable text files. Before it becomes visible online, it goes through a build process:

1. **Writing** — You create content in the appropriate area (documentation, blog, or custom pages)
2. **Organizing** — You set up the navigation (a sidebar or a navigation map)
3. **Building** — You run the build command, which converts all source content into finished web pages
4. **Deploying** — You publish the finished output to a hosting service

The build output is a folder of ready-to-serve files: HTML pages, stylesheets, images, and supporting assets. Visitors interact with this output—never the raw source content. The build step also validates your content: broken links can be set to stop the build entirely, preventing broken pages from reaching readers.

### Deployment Settings

The Docusaurus configuration includes deployment details that determine where the site will live. These include:

- **The production URL** — the final web address
- **The base path** — where on that domain the site is served
- **Organization and project names** — used to generate GitHub Pages links and the "edit this page" buttons

For MkDocs, deployment is simpler: after the build produces the finished pages, you host them on any static file server or hosting service.

## Summary

| Concept | Docusaurus | MkDocs Material |
|---|---|---|
| Documentation pages | In a dedicated documentation area, auto-organized into a sidebar | Listed explicitly in the navigation map |
| Blog | Built-in with authors, tags, RSS, and reading time | Not included |
| Custom pages | Fully supported | Limited |
| Navigation | Automatic from folder structure or manually defined | Single explicit navigation map |
| Metadata | Front matter with title, slug, authors, tags | YAML configuration for site and navigation |
| Build output | Finished web pages ready for hosting | Finished web pages ready for hosting |

**The key takeaway:** Source content is what you write and organize. The build process transforms it into a finished website. Understanding this flow—write, organize, build, deploy—is the foundation for everything else on this platform.
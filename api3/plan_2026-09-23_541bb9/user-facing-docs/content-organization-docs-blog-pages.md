# Content Organization: Docs, Blog, Pages

This guide explains where to place different types of content in your documentation site so visitors can easily find what they need. You will learn about four key content areas and how they connect to the URLs your readers see.

---

## 1. Documentation Articles (the `docs` Directory)

The `docs` directory is the home for your **long-form reference material**. This is where step-by-step tutorials, concept explanations, quick-start guides, and API references live.

### How Documents Are Organized

Each document is a Markdown file. The name of the file determines its place in the navigation sidebar and its final URL. For example, a file named `getting-started.md` becomes a page visitors reach at a URL ending in `/getting-started`.

You can group related documents into subfolders. A folder named `tutorials` containing a file called `installation.md` creates a navigation section called "Tutorials" with a page inside it.

### The Sidebar Is Created Automatically

You do not need to manually build a navigation menu. The sidebar is generated from the files and folders inside the `docs` directory. The order of items follows the order of files and folders, though you can adjust ordering using a dedicated configuration file if needed.

**Best place for:** Reference guides, how-to articles, conceptual explanations, and any content that benefits from a structured table of contents.

---

## 2. Blog Posts (the `blog` Directory)

The `blog` directory holds **time-sensitive content** such as announcements, release notes, company news, and update posts.

### How Blog Posts Are Organized

Each blog post is a Markdown file with a special section at the top containing post details such as the title, author names, publication date, and tags. This information is used by the site to sort posts, display author attribution, and generate the blog listing page.

The recommended file naming convention is to include the date at the beginning of the filename, such as `2024-06-15-release-notes.md`. This keeps your posts easy to scan and helps the system understand when each post should be published.

### Blog Features

- Posts appear in reverse chronological order on the main blog page
- Tags automatically create filtered views of related posts
- A sidebar lists recent posts so readers can jump to other articles
- Each post has a dedicated permalink that remains stable over time

**Best place for:** Announcements, release notes, team updates, and any content tied to a specific date.

---

## 3. Standalone Pages (the `src/pages` Directory)

The `src/pages` directory is used for **independent pages** that do not belong to the documentation sidebar or the blog. These are typically the pages people land on first, such as a home page, an about page, or a contact page.

### How Standalone Pages Work

Each page is a file that uses a common format for building interactive web pages. The site automatically converts each file in this directory into a full page with a URL matching the file's name.

For example, a page file named `about` becomes reachable at a URL ending in `/about`. A file named `index` becomes the site's homepage at the root URL.

### When to Use a Standalone Page

- Marketing or landing pages with custom visual layouts
- Pages that need interactive elements not typically used in documentation
- A custom homepage distinct from the documentation landing page

**Best place for:** Homepage, about page, contact page, and any custom page that deserves a unique design separate from the documentation structure.

---

## 4. Static Assets (the `static` Directory)

The `static` directory holds **files that are served to visitors exactly as they are**, with no processing or transformation. This includes images, downloadable PDFs, fonts, favicon icons, and other files that your pages link to.

### How Static Assets Work

When you place a file in the `static` directory, it becomes available at a predictable URL based on its location within that directory. A file placed at `static/img/logo.png` is accessible at a URL ending in `/img/logo.png`.

You reference these assets from your documents, blog posts, and pages using that URL. This means you can use the same image across multiple pages by placing it once in the `static` directory.

### Common Uses

- Logos and brand imagery
- Screenshots embedded in documentation articles
- Downloadable files such as brochures or data sheets
- Favicon and other site icons

**Best place for:** Any file that should be directly accessible via a URL and does not require the site to process or transform it.

---

## 5. URL Routing and the Base URL

Every piece of content you create gets a **predictable URL** based on where you place it.

### How URLs Are Built

| Content Type | Where You Put It | Resulting URL Path |
|---|---|---|
| Documentation | `docs` directory | `/docs/your-file-name` |
| Blog post | `blog` directory | `/blog/your-post-name` |
| Standalone page | `src/pages` directory | `/your-page-name` |
| Static asset | `static` directory | `/your-file-path` |

The source directory (`docs`, `blog`, `src/pages`, `static`) maps directly onto the first segment of the URL.

### The Base URL Setting

The base URL is a configuration value that determines the **root path** where your entire site is hosted. This matters when your site is not hosted at the top level of a domain.

For example, if your site is hosted at a location like `example.com/project-name/`, then the base URL must be set to `/project-name/`. All content URLs would then begin with `/project-name/` — for instance, your documentation index would be at `/project-name/docs/`.

Adjust this setting before deploying your site, because changing it later affects every link on the site.

---

## Quick Reference: Where Should Each Piece of Content Go?

| You Want to Create... | Put It Here |
|---|---|
| A long-form tutorial or reference guide | `docs` directory |
| A dated announcement or release note | `blog` directory |
| A custom homepage or marketing page | `src/pages` directory |
| An image, PDF, or downloadable file | `static` directory |
| A global setting affecting all URLs | Base URL configuration |

---

## Summary

Content organization follows a clear, predictable pattern:

1. **Documentation** lives in the `docs` directory and generates an automatic sidebar.
2. **Blog posts** live in the `blog` directory, require date and author details, and appear in reverse chronological order.
3. **Standalone pages** live in the `src/pages` directory for custom, non-documentation pages.
4. **Static files** live in the `static` directory and are served without modification.
5. **URLs** are generated from where you place each file, with the base URL acting as the common prefix for the entire site.

By following these conventions, you ensure that readers can always find content in a predictable location, and that as your site grows, everything remains organized and easy to navigate.
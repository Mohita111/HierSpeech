# How to Configure the Docusaurus Site

Your Docusaurus site has one master settings file that controls everything from the site name to the footer links. This guide explains each section and shows exactly what to change when you rebrand the site and point it to your own organization and hosting URL.

## 1. Site Identity: Title, Tagline, Favicon, URL, and Base URL

These settings define who the site is and where it lives.

### Site Title
The site title appears in the browser tab and in the hero section of the homepage. The default value is **My Site**.

**Change this to your organization or project name**, for example:

```
title: 'Your Project Name',
```

### Tagline
The tagline appears below the title on the homepage. The default is **Dinosaurs are cool**.

Replace it with a short description of your site:

```
tagline: 'Documentation for your product or team',
```

### Favicon
The favicon is the small icon shown in the browser tab. The default points to an image file named `favicon.ico` inside the images folder. Keep this setting unchanged if you replace that image with your own icon. If you use a different file name, update it here.

```
favicon: 'img/favicon.ico',
```

### Production URL
This is the full web address where your published site will live. The default placeholder is `https://your-docusaurus-site.example.com`.

Replace it with your real domain, such as:

```
url: 'https://docs.example.com',
```

### Base URL
The base URL is the path under your domain where the site is served.

- If your site is at the root of the domain, use `/`.
- If you are deploying as a GitHub Pages project site, use the repository name in slashes, for example `/my-repo/`.

The current setting is:

```
baseUrl: '/',
```

## 2. GitHub Pages Settings: Organization and Project Name

If you plan to deploy the site using GitHub Pages, these two values must match your GitHub account and repository.

- **organizationName** is your GitHub username or organization name. The placeholder is `facebook` — replace it with your actual GitHub name.
- **projectName** is your GitHub repository name. The placeholder is `docusaurus` — replace it with your repo name.

Example:

```
organizationName: 'your-github-org',
projectName: 'your-repo-name',
```

If you are not using GitHub Pages, you can leave these as they are or remove them.

## 3. Broken Link Handling and Future Compatibility Flag

These settings control how the site behaves during a build and its readiness for upcoming Docusaurus versions.

### Broken Link Handling
The `onBrokenLinks` setting determines what happens when the build process finds a link that points to a missing page.

- `'throw'` — The build fails and stops (current setting). This is best for catching broken links before publishing.
- `'warn'` — The build completes but prints a warning for each broken link.
- `'ignore'` — Broken links are silently ignored.

Choose `'throw'` for strict quality control, or change to `'warn'` if you prefer a temporary warning.

### Future Version Compatibility Flag
The setting `future: { v4: true }` enables compatibility with the upcoming Docusaurus v4. Leave this set to `true` to prepare the site for the next major version.

## 4. Classic Preset: Docs, Blog, Theme, and Syntax Highlighting

The site uses the **classic preset**, which bundles the documentation, blog, and theme features into one configuration.

### Docs Settings
The docs section includes:
- A sidebar configuration file (no changes needed unless you customize sidebars).
- An **edit URL** that points to the GitHub repository. The current edit URL still points to the Docusaurus template repository. **Replace this with your own repository URL** so the “Edit this page” links work correctly.

### Blog Settings
The blog section includes:
- **Reading time** enabled — each blog post shows an estimated read time.
- **RSS and Atom feeds** — blog posts are available as feeds for subscribers.
- **Edit URL** — same as docs, replace with your own repository URL.
- **Writing best practices warnings** — the blog warns if posts are missing inline tags, missing authors, or are not truncated on the listing page. These are set to `'warn'` and can be left as is.

### Theme Settings
The theme section points to a custom CSS file that controls the site’s appearance. If you add custom styles, keep this path; no change is needed for basic rebranding.

### Syntax Highlighting
Code blocks use the `prism-react-renderer` tool with two color themes:
- Light mode: **GitHub** theme
- Dark mode: **Dracula** theme

You can keep these themes or replace them with any other Prism theme that suits your branding.

## 5. Navbar Customization

The navigation bar at the top of every page has these configurable parts:

### Title
The navbar title currently shows **My Site**. Change it to your project name, matching the site title.

### Logo
The navbar has a logo with:
- An image file (`img/logo.svg`)
- Alt text (**My Site Logo**) — update this to describe your logo for screen readers.

Replace the logo image with your own and update the alt text accordingly.

### Menu Items
The navbar includes three items:
- **Tutorial** — a left-side link that opens the documentation sidebar. Update the label and the sidebar reference to match your own docs.
- **Blog** — a left-side link to the blog page. Keep or relabel as needed.
- **GitHub** — a right-side button linking to the GitHub repository. The current link points to `https://github.com/facebook/docusaurus`. **Replace this with your own GitHub repository URL.**

## 6. Footer Customization

The footer has three link columns and a copyright line.

### Link Columns
- **Docs** — contains a link to the tutorial page (`/docs/intro`). Update the link and label to point to your main documentation page.
- **Community** — currently links to Stack Overflow, Discord, and X (all Docusaurus community pages). Replace these with your own community links or remove them.
- **More** — contains links to the Blog and GitHub. Update the GitHub link to your repository.

### Copyright
The footer includes a copyright line that automatically shows the current year. The text says:

```
Copyright © 2024 My Project, Inc. Built with Docusaurus.
```

Replace **My Project, Inc.** with your organization or legal entity name. The year updates automatically each year; you do not need to manually change it.

## 7. Rebranding Checklist

Use this checklist when you are ready to rebrand and repoint the site:

1. Replace **title** and **tagline** with your organization name and description.
2. Replace **url** with your real production domain.
3. Set **baseUrl** to `/` for root hosting or `/repo-name/` for GitHub Pages project hosting.
4. Set **organizationName** and **projectName** to your GitHub username and repository name.
5. Update all **editUrl** values (docs and blog) to your own repository URL.
6. Update navbar **title**, **logo alt text**, and replace the logo image.
7. Update the navbar **GitHub** link to your repository.
8. Update footer link labels and URLs to your own docs, community, and GitHub pages.
9. Update the copyright text to include your organization name.
10. Replace the favicon file with your own icon.
11. Optional: replace the social card image (`img/docusaurus-social-card.jpg`) with your own preview image.

After making these changes, save the settings file and rebuild or restart the site to see your rebranded version.
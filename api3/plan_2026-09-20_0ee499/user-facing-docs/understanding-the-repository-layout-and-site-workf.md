# Understanding the Repository Layout and Site Workflow

This repository contains two separate websites, plus one standalone guide document. Each website has its own purpose, publishing process, and audience. Knowing the difference helps you make changes in the right place and understand how those changes go live.

## 1. The two website areas at a glance

| Area | What it is for | How it is published |
|------|----------------|---------------------|
| Product website area | Homepage, product documentation, tutorials, and blog | Published manually using a deployment command |
| DigitalOcean documentation area | Internal infrastructure and DigitalOcean deployment guides | Published automatically by GitHub Actions whenever updates are saved to the main branch |
| Top-level guide document | A standalone written guide that sits outside the two website areas | Not part of either website's automatic publishing path in the available information |

These two websites are independent. Editing one does not automatically update the other.

## 2. Which area should you edit?

The rule is simple: match the type of content to the site that hosts it.

### Edit the DigitalOcean documentation area for deployment and infrastructure guides

Use this area when you need to change or add step-by-step deployment blueprints for tools running on DigitalOcean. The current guides include:

- Bitwarden Deployment
- CSI for S3
- OpenLIT
- Pangolin (Community Edition)

This site is an internal documentation hub for technical setup workflows.

### Edit the product website area for product-facing content

Use this area when you need to update:

- The homepage and marketing text
- Product documentation and tutorials
- The documentation sidebar
- Blog posts
- General navigation links, footer links, or theme styling

This site is the outward-facing product website. In the current source, it still shows placeholder starter content, including the name "My Site" and the tagline "Dinosaurs are cool."

### What about the top-level guide document?

There is also a standalone written guide at the top level of the repository. The available source does not show how or whether this guide is automatically published. Treat it as a separate overview document unless you confirm otherwise in the live repository.

## 3. The publishing workflow for the DigitalOcean documentation site

This site uses an automated workflow. The workflow is triggered when changes are pushed to the main branch.

The process is:

1. You edit the DigitalOcean documentation content.
2. You save and push your changes to the main branch.
3. GitHub Actions detects the update.
4. The workflow sets up the required website-building tools.
5. The documentation site is built.
6. The finished site is uploaded and deployed to GitHub Pages automatically.

No manual deployment step is needed. The publishing pipeline runs entirely from GitHub Actions.

## 4. The publishing workflow for the product website

This site does not use the same automatic GitHub Actions path. It must be published manually using Docusaurus commands.

The lifecycle is:

1. **Edit** the product website content.
2. **Preview locally** by starting a local development server. Most changes appear live in the browser without restarting the server.
3. **Build** the final site to generate the finished static content.
4. **Deploy** manually by running the deployment command. This builds the website and pushes the result to the `gh-pages` branch.

For the deployment step, the available documentation provides two options:

- Deploy using SSH with `USE_SSH=true yarn deploy`
- Deploy using GitHub credentials with `GIT_USER=<Your GitHub username> yarn deploy`

The deployment command is the manual step that publishes the product website. It is not triggered automatically by pushing to the main branch.

## 5. How the homepage, docs sidebar, and blog fit together

The product website navigation connects the homepage, documentation, and blog.

### Navigation links

The top navigation includes:

- **Tutorial** — opens the documentation section and displays its sidebar
- **Blog** — opens the blog section
- **GitHub** — links to an external GitHub project page

### Footer links

The footer also includes:

- A **Docs** section with a link to the Tutorial
- A **Community** section with links to Stack Overflow, Discord, and X
- A **More** section with links to the Blog and GitHub

### Blog behavior

The blog section shows the estimated reading time for each post and provides subscription feeds through RSS and Atom.

### Documentation sidebar

The product website documentation section uses a sidebar named `tutorialSidebar`. The top navigation item labeled "Tutorial" points to this sidebar, so users can click "Tutorial" in the main menu to enter the product documentation area and navigate using the sidebar.

## 6. Summary: where does a change go and how does it reach production?

| Change type | Location to edit | Publishing method |
|-------------|------------------|-------------------|
| DigitalOcean deployment guide such as Bitwarden, CSI for S3, OpenLIT, or Pangolin | DigitalOcean documentation area | Automatic on push to main via GitHub Actions |
| Homepage, product docs, tutorial sidebar, or blog content | Product website area | Manual build and deploy using the deployment command |
| Standalone written guide | Top-level guide document | Not enough information in the available source to determine publishing behavior |

In short: make DigitalOcean deployment guide changes in the DigitalOcean documentation area, and they will publish automatically. Make product website changes in the product website area, and publish them manually with the deployment command.
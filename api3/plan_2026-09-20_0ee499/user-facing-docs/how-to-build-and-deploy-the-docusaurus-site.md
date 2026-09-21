# How to Build and Deploy the Docusaurus Site

This guide explains how to turn your website into a publishable set of files and put it on GitHub Pages from start to finish.

## What You’ll Need

- A copy of the website project on your computer.
- Dependencies installed. If you haven’t installed them yet, run `yarn` once.
- Node.js version 20 or newer.
- A GitHub account and a repository where you want to publish the site.

## 1. Building the Site

1. Open a terminal in the website project folder.
2. Run:

```bash
yarn build
```

This command creates a folder called `build` containing the finished website files. These are the files that will be served to visitors and can be hosted on any static hosting service.

## 2. Previewing the Production Build

To see exactly what will be published after deployment, run:

```bash
yarn serve
```

This starts a local server for the finished files in the `build` folder. Use it to verify that everything looks correct before you publish.

`yarn serve` shows the production output, not the development version.

## 3. Deploying to GitHub Pages

The deployment command builds the site and pushes it to a special `gh-pages` branch. GitHub Pages then publishes that branch automatically.

Choose one of the two methods below.

### Option A: Using SSH

If your GitHub account is set up for SSH, run:

```bash
USE_SSH=true yarn deploy
```

This uses your SSH credentials to connect to GitHub.

### Option B: Using HTTPS with your GitHub username

If you use HTTPS with a personal access token or GitHub password, run:

```bash
GIT_USER=YourGitHubUsername yarn deploy
```

Replace `YourGitHubUsername` with your actual GitHub username.

> The deployment command is a convenient way to build the website and push it to the `gh-pages` branch in one step.

## 4. How the Deployment Target Is Determined

Your site’s configuration includes two important settings:

- **GitHub organization or username** — usually your GitHub user or organization name.
- **Project or repository name** — usually the name of the repository that holds your site.

Together, these settings determine where the `gh-pages` branch is pushed. For example, if your GitHub username is `alice` and your repository is `my-site`, the deployment will publish to that repository’s GitHub Pages location.

You should also update:

- **Site URL** — set this to your actual GitHub Pages URL. For a project site, this is usually `https://your-username.github.io`.
- **Base path** — for a project site, this is often `/<repository-name>/`. For a user or organization site, it is usually `/`.

The starter values are placeholders, so replace them with your own details before deploying.

## 5. Clearing Caches When Builds Misbehave

If the build produces errors or shows stale content, clear temporary files with:

```bash
yarn clear
```

This removes generated files and caches, which can resolve strange behavior during build or serving. After clearing, run `yarn build` again.

## End-to-End Checklist

1. Run `yarn` to install dependencies if you haven’t already.
2. In your site configuration, set your GitHub username or organization, repository name, site URL, and base path.
3. Run `yarn build` to create the finished website files.
4. Run `yarn serve` to preview the production output locally.
5. Run either:
   - `USE_SSH=true yarn deploy` if using SSH, or
   - `GIT_USER=YourUsername yarn deploy` if using HTTPS.
6. Visit your GitHub Pages URL to confirm the site is live.
# Installation and First Local Preview

This guide walks you through getting both local websites running on your computer for the first time and confirming that live editing works.

## Before You Start

Make sure you have these tools installed:

- **Git** — used to download the project
- **Node.js version 20 or newer** — required by the main website
- **Yarn** — used to install and run the main website
- **Python 3** and **pip** — used by the DigitalOcean documentation site

If you are missing any of these, install them from their official websites before continuing.

## Step 1: Download the Project

1. Open a terminal on your computer.
2. Go to the repository page in your browser.
3. Click the **Code** button and copy the HTTPS or SSH address.
4. In your terminal, run `git clone` followed by the address you copied.

After the download finishes, move into the downloaded folder. Inside it, you will see two separate website areas:

- The **main website area** — often named `my-website`
- The **DigitalOcean documentation area** — often named `DigitalOcean-Docs`

Each area is independent, so you will install and run them separately.

## Step 2: Start the Main Website

The main website uses Docusaurus and runs through Yarn.

1. Open a terminal window inside the main website folder.
2. Install the required dependencies:

```bash
yarn
```

3. Start the local preview server:

```bash
yarn start
```

The `yarn start` command starts a local development server and usually opens a browser window automatically. If it does not, your terminal will show the local address you can open.

The server will keep running in that terminal window. Most changes you make are reflected live without restarting the server.

## Step 3: Start the DigitalOcean Documentation Site

The DigitalOcean documentation site uses MkDocs with the Material theme.

1. Open a second terminal window or tab inside the DigitalOcean documentation folder.
2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

This installs MkDocs and the Material theme.

3. Start the documentation preview server:

```bash
mkdocs serve
```

Your terminal will show a local address, usually on port 8000. Open that address in your browser.

Keep this terminal running as well. You now have both sites running at the same time.

## Step 4: Verify the Pages Work

### Main Website

Check the following:

- The homepage loads correctly.
- The top navigation includes the standard sections.
- The **Docs** and **Blog** pages open and display content.

### DigitalOcean Documentation Site

Check the following:

- The **Welcome** page loads correctly.
- The navigation includes a **Core Integrations** section with these pages:
  - **Bitwarden Deployment**
  - **Storage with CSI for S3**
  - **Observability via OpenLIT**
  - **Database Cluster with Pangolin (CE)**

Click each page in the navigation to confirm the content appears and the sidebar behaves as expected.

If a page does not load, check the matching terminal window for any error messages.

## Step 5: Make a First Live Edit

Both servers should still be running.

1. Leave both terminals open.
2. For the main website, find a Markdown file that holds one of the Docs pages. Files end in `.md`. Change a heading or a sentence, then save the file.
3. For the DigitalOcean documentation site, open a Markdown file named after one of the pages you just viewed, such as the Welcome page. Change a sentence, then save the file.

After you save, watch the browser tab. The page should refresh automatically, and your change should appear immediately. This confirms that live editing works for both sites.

## Summary

You now have:

- The main website running locally from the first terminal
- The DigitalOcean documentation site running locally from the second terminal
- Live reload working — saved Markdown edits appear without restarting either server

When you are finished, you can stop each site by pressing `Ctrl + C` in that terminal window.
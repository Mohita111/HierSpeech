# Installing Docusaurus and Creating a New Site

This guide shows you how to create a new Docusaurus documentation website on your own computer.

## Before You Begin

Make sure your computer has:

- Node.js 18 or newer
- npm, Yarn, or pnpm installed
- A terminal application

You can check your Node.js version with:

```bash
node -v
```

If you do not have Node.js installed, download it from the official Node.js website first.

## Step 1: Create a New Project

Run one of these commands in your terminal. Replace `my-website` with the folder name you want.

Using npm:

```bash
npm init docusaurus@latest my-website classic
```

Using Yarn:

```bash
yarn create docusaurus my-website classic
```

Using pnpm:

```bash
pnpm create docusaurus@latest my-website classic
```

The final word `classic` selects the template.

## Step 2: Choose a Template

Docusaurus can create different starting layouts:

- **classic** — includes documentation, a blog, and a customizable homepage. Best for most teams.
- **bootstrap** — a lighter starting point focused on documentation without the extra blog setup.
- **Your own shared template** — if your organization has a standard template, use its name in place of `classic`.

If you are not sure which one to choose, use `classic`.

## Step 3: Move Into the Project Folder

After the command finishes, go into the new folder:

```bash
cd my-website
```

## Step 4: Install Dependencies

If the creation command did not automatically install dependencies, run one of these:

```bash
npm install
```

```bash
yarn install
```

```bash
pnpm install
```

This downloads the packages your site needs to run.

## Step 5: Start the Development Site

Run one of these commands:

```bash
npm run start
```

```bash
yarn start
```

```bash
pnpm start
```

After it starts, open `http://localhost:3000` in your browser. You should see your new site with the default Docusaurus homepage.

## Step 6: Understand the Folders That Were Created

Inside the new project folder you will find:

- A main configuration file that controls the site title, tagline, URL, navigation bar, and footer.
- A documentation folder where you add help articles as Markdown files.
- A blog folder where you add news posts or release announcements.
- A pages folder where you can add standalone pages like a homepage.
- A static folder for images, PDFs, and other files that do not need processing.
- A sidebar file that controls the table of contents for the documentation section.

This structure is ready to use immediately.

## Step 7: Adjust Basic Settings

Open the main configuration file named `docusaurus.config.js` in a text editor. The top section looks similar to this:

```js
module.exports = {
  title: 'My Site',
  tagline: 'A place to share documentation',
  favicon: 'img/favicon.ico',
  url: 'https://example.com',
  baseUrl: '/',
  organizationName: 'my-org',
  projectName: 'my-website',

  themeConfig: {
    navbar: {
      title: 'My Site',
      logo: {
        alt: 'My Site Logo',
        src: 'img/logo.svg',
      },
      items: [
        { to: '/docs/intro', label: 'Docs', position: 'left' },
        { to: '/blog', label: 'Blog', position: 'left' },
      ],
    },
    footer: {
      style: 'dark',
      copyright: `Copyright © ${new Date().getFullYear()} My Site`,
    },
  },
};
```

Change the following settings to match your project:

- `title` — the name shown in the browser tab and navigation bar
- `tagline` — a short description of the site
- `url` — the final website address
- `baseUrl` — keep as `/` for most sites
- `organizationName` and `projectName` — used when publishing to GitHub Pages

After saving the file, go back to your browser. The development site usually updates automatically.

## Step 8: Confirm the Project Is Healthy

Stop the development server if needed, then run:

```bash
npm run build
```

```bash
yarn build
```

```bash
pnpm build
```

A successful build means your project folder is complete and ready to be edited or published.

## Common Issues

- **“Command not found” after running npm or yarn**: install Node.js first.
- **Port 3000 is already in use**: run the start command with a different port, for example:

```bash
npm run start -- --port 3001
```

- **Old Node.js version**: upgrade to Node.js 18 or newer, then run the create command again.

Once these steps are complete, you have a working Docusaurus project folder. You can begin writing documentation, customizing the homepage, and adding blog posts.
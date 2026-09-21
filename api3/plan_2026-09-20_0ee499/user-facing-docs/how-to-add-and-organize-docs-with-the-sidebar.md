# How to Add and Organize Docs with the Sidebar

This guide explains how to create new documentation pages and control where they appear in the left-hand navigation sidebar.

## Understanding How the Sidebar Works

By default, the documentation sidebar builds itself automatically from the folder structure of your documentation area.

- Each folder becomes a section in the sidebar.
- Each documentation page appears under its containing folder.
- Pages placed directly at the top level appear as top-level entries.

For example, the existing **DigitalOcean Content** section groups two pages together:

- **Docusaurus**
- **How to Tag Droplets**

Both pages appear under the same sidebar heading because they are stored together in the same folder.

## Adding a New Documentation Page

To add a new page:

1. Open your documentation collection.
2. Navigate to the folder where the new page should appear.
3. Create a new documentation file with a clear, descriptive name.
4. Add a title and optional description at the top of the document.
5. Save the file.

The sidebar updates automatically. The new page appears in the section that matches its folder location.

## Page Settings You Can Set at the Top

Each documentation page can include a settings block at the very top. These settings control how the page appears in navigation and search results.

Common settings include:

| Setting | What It Does |
|---------|-------------|
| **Title** | The name shown in the sidebar and at the top of the page. |
| **Description** | A short summary used in search results and link previews. |
| **Slug** | An optional custom web address for the page. If you do not set one, the address is created automatically from the file location. |
| **Last Updated** | The date the page was last reviewed or changed. |

Additional reference fields such as a product name or source URL can also be included. The existing **How to Tag Droplets** page demonstrates this with a clear title, a descriptive summary, and a last-updated date.

## Organizing Pages into Folders

You can group related guides by creating folders inside the documentation area.

To create a new group:

1. Create a new folder with a descriptive name.
2. Place related documentation pages inside that folder.
3. Save your changes.

The folder name becomes a heading in the sidebar, and all pages inside it are listed beneath that heading.

For example, placing a new page inside the existing **DigitalOcean Content** folder makes it appear under that same sidebar section.

## Switching to a Manually Arranged Sidebar

In addition to the automatic sidebar, the documentation configuration includes a prepared manual layout. By default, the manual layout is turned off, while the automatic layout is active.

If you switch to the manual layout, you can:

- Choose the exact order of pages in the sidebar.
- Create collapsible categories with custom labels.
- Decide which pages appear first and which appear inside a category.

For example, the prepared manual layout defines a category labeled **Tutorial** that contains a specific page. You can follow this pattern to create your own ordered sections.

## Step-by-Step Example: Add a Page Under DigitalOcean Content

Follow these steps to add a new guide that appears in the existing **DigitalOcean Content** sidebar section:

1. Open your documentation collection.
2. Open the **DigitalOcean Content** folder.
3. Create a new documentation file named after your topic, such as **How to Create a Project**.
4. At the top of the file, set a clear title and a short description.
5. Save the file.
6. Open the documentation section of your site and confirm that the new page appears under **DigitalOcean Content**.

If you are using the automatic sidebar, the new page joins the other pages in that section automatically. If you have switched to a manual sidebar, add the new page to the desired position in the manual layout.
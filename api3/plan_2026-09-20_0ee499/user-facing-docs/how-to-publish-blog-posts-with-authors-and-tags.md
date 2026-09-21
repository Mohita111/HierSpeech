# How to Publish Blog Posts with Authors and Tags

This guide explains how to create blog posts, assign authors and topic labels, add images, control the preview text shown in blog lists, and manage author and topic pages. It also covers how to turn the blog off completely if you do not need it.

## What you can do

With the blog feature you can:

- Publish posts that are automatically organized by date.
- Give each post a title, a custom web address, one or more authors, and one or more topic labels.
- Store images next to the post so they are easy to manage.
- Mark where the list preview should stop, so only the introduction appears on the main blog page.
- Create dedicated pages for authors and topics.
- Add social links to author profiles.
- Disable the blog entirely if it is not needed.

## Creating a post

Every blog post is stored as a dated entry. The date is taken from the entry name itself, such as:

- `2019-05-30-welcome`
- `2019-05-30-welcome/index`

A post can be a single dated entry, or a dated folder that contains the post and related images together. A folder is useful when you want to keep pictures beside the text they belong to.

For example, the welcome post is dated `2021-08-26` and is stored as a folder so its banner image can live in the same place.

## Adding post details

At the top of a post, you provide basic publication details:

- **Web address** — The ending of the post’s URL. For example, the welcome post uses `welcome`.
- **Title** — The headline shown on the page and in lists. The welcome post uses the title **Welcome**.
- **Authors** — The people credited with the post. You list them by the same names registered in your author profiles. The welcome post credits **Sébastien Lorber** and **Yangshun Tay**.
- **Topics or tags** — The labels that group related posts. The welcome post uses three labels: **Facebook**, **Hello**, and **Docusaurus**.

These details control how the post appears in lists, on its own page, and on author and topic pages.

## Adding images

To include an image in a post, place the image file in the same folder as the post. Then insert the image into the content using its filename.

The welcome post demonstrates this by displaying a Docusaurus plush toy banner image that is stored in the same folder as the post text.

## Controlling list previews

Blog list pages usually show only a short introduction rather than the full post. You control where that introduction stops by placing a cut-off marker in the content.

In the welcome post, the marker is placed immediately after the sentence:

> Here are a few tips you might find useful.

Everything before the marker appears as the preview. Everything after it appears only on the full post page.

If a post has no cut-off marker, the site can warn you so the full post does not accidentally appear in list pages.

## Registering authors

Author profiles store everything needed to credit a writer:

- The author’s display name.
- A title or role.
- A personal website link.
- A profile picture link.
- Whether the author should have a dedicated page that lists all their posts.
- Social profile links.

For example, **Yangshun Tay** is registered with the title **Ex-Meta Staff Engineer, Co-founder GreatFrontEnd**, a LinkedIn profile link, a profile picture, and social links for X, LinkedIn, GitHub, and a newsletter.

**Sébastien Lorber** is registered with the title **Docusaurus maintainer**, a personal website, and social links for X, LinkedIn, GitHub, and a newsletter.

Authors can also have their own page address customized. For example, Sébastien Lorber’s author page can be reached at:

`/all-sebastien-lorber-articles`

When you credit an author in a post, use the registered author name exactly as it appears in the author settings.

## Registering topic labels

Topic labels group posts by shared subject. Each label has:

- A display name, which appears on the blog.
- A web address, which controls the topic page URL.
- A short description that explains the topic.

Example topic labels include:

- **Facebook** — web address `/facebook`, description “Facebook tag description”
- **Hello** — web address `/hello`, description “Hello tag description”
- **Docusaurus** — web address `/docusaurus`, description “Docusaurus tag description”
- **Hola** — web address `/hola`, description “Hola tag description”

When you add a topic to a post, use the registered label name exactly as it appears in the topic settings. Topic pages automatically list all posts that share that label.

## Quick workflow: publish a fully attributed, tagged post

Follow these steps to publish a complete blog post:

1. Open the blog content area.
2. Create a dated entry for the post. Use a single dated entry for text only, or use a dated folder if you need to include images.
3. Add the post content and insert any images from the same folder.
4. Provide the web address, title, author names, and topic labels at the top of the post.
5. Place the cut-off marker after the introductory text.
6. If a needed author is not already registered, add the author’s profile with display name, title, website, picture, social links, and any custom author page address.
7. If a needed topic label is not already registered, add the label with its display name, web address, and description.
8. Save the post. The blog list, author pages, and topic pages will now include the post automatically.

## Turning the blog off

If you do not want a blog on your site, you can disable it entirely. The site then stops showing the blog section and its associated pages.

The welcome post notes this directly: if you don’t want a blog, remove the blog content area and set the blog feature to **off** in your site settings.
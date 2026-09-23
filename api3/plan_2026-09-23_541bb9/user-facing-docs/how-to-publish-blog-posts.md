# How to Publish Blog Posts

Publishing a blog post on your site is done by creating a new document in the blog area and adding a short settings block at the top. This guide walks through each step so you can publish your first post with metadata and a preview summary.

## 1. Add a New Post in the Blog Area

All blog posts live in the blog folder of your site. To publish a new post, create a new document inside that folder and write your content below the settings block.

Your post can include headings, bullet points, images, and links, just like any other page on your site.

## 2. Name the Post with a Date

Each post document must be named using the date it is published, followed by a short title. The format is:

```
YYYY-MM-DD-post-title.md
```

For example, for a post published on March 5, 2025 called “My First Post,” the document name would be:

```
2025-03-05-my-first-post.md
```

The date in the name controls when the post appears on the blog page. Posts with earlier dates are shown before later posts.

## 3. Add Post Settings for Title, Authors, and Tags

At the very top of your post document, add a settings block that contains key information about the post. The settings block is marked by two lines of three dashes. Inside it, you can include:

- **title** — the headline of your post
- **authors** — who wrote the post (you can list one or more names)
- **tags** — short labels that help visitors find related posts

Example settings block for a post titled “My First Post,” written by “Jane Doe,” with tags “Announcement” and “Updates”:

```
---
title: My First Post
authors: Jane Doe
tags: [Announcement, Updates]
---
```

After the closing three dashes, write the main content of your post.

Tags can be a single tag or a list of several tags. When visitors click a tag, they see all posts with that tag.

## 4. Create a Summary for the Post List

On the main blog page, posts are shown as cards with a short introduction. By default, the beginning of the post is used as this preview. To control exactly where the preview ends, place a special marker in the body of your post:

```
<!-- truncate -->
```

Everything above this marker becomes the summary shown in the blog list. Everything below is only visible when a visitor opens the full post. This is useful for keeping the list tidy and hiding long introductions until the reader opens the post.

## 5. Adjust How Many Posts Appear Per Page

You can control how many post summaries appear on a single blog page. In your site’s blog settings, look for the option called **“posts per page”** (also shown as `postsPerPage` in the settings panel). Set this to the number you want, for example 3, 5, or 10.

When you save the setting, the blog page shows that many posts per page and automatically adds navigation links so visitors can move to older or newer posts.

---

Once you have added a post document, included the settings block, and saved the file, your post will appear on the blog page automatically, sorted by its date. Repeat these steps for each new post. To update an existing post, open its document, make your changes, and save again.
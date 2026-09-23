# Understanding Docusaurus Architecture and Plugins

> **Source note:** The repository snapshot provided for this documentation (HierSpeech requirements.txt) contains Python package dependencies for a speech synthesis research project and does not include Docusaurus implementation code. This document delivers the conceptual overview described in the planning notes. For the latest implementation-specific details, refer to the official Docusaurus API reference.

---

## Introduction

Docusaurus is a website framework designed to help teams build documentation sites quickly. Its real power comes from how it is put together: a small, stable core surrounded by a flexible system of add-ons that can change nearly everything about how the site looks and behaves.

This document explains the building blocks of Docusaurus, how they fit together, and where you can customize each part.

---

## Core vs. Plugins vs. Themes

Docusaurus is organized into three distinct layers:

### The Core

The core is the foundation. It handles the essential work every site needs: reading your content, assembling pages, building the navigation, and producing the final set of static files that get served to visitors. The core is deliberately kept small and stable. It does not make assumptions about how your site should look or what extra features it should have.

### Plugins

Plugins add *capabilities*. A plugin might add a blog, enable search, produce a sitemap, or generate documentation pages. Each plugin is independent: you can add or remove plugins without altering the core. Plugins communicate with the core through a well-defined agreement about what information they receive and what they return.

### Themes

Themes control *appearance and structure*. A theme supplies the visual design, the page layouts, the navigation bars, and the interactive components visitors interact with. Docusaurus thinks of every theme as a special kind of plugin—one whose primary job is to provide presentation rather than data processing. A site can use one theme or combine several.

**In plain terms:** the core is the engine, plugins are the factory machines that produce content, and themes are the showroom floor where visitors see the result.

---

## Presets: Bundled Configurations

Setting up a documentation site typically requires several plugins and a theme working together. Instead of requiring you to configure each one individually, Docusaurus offers **presets**.

A preset is a pre-packaged collection of plugins and themes that are known to work well together. The most widely used is the **classic preset**, which bundles:

- The standard documentation plugin
- The blog plugin
- The pages plugin
- The classic theme that gives the site its familiar look
- Several supporting plugins for features like sitemap generation and color mode

When you use a preset, you turn an entire feature set on or off with a simple yes/no choice—rather than wiring up a dozen individual components. Presets can also forward specific settings to each bundled plugin, letting you customize behavior while still benefiting from the sensible defaults.

The classic preset is not the only option. Teams with specific needs can create their own presets, bundling only the plugins and themes their site actually requires.

---

## The Lifecycle of a Build

When Docusaurus builds your site—whether for local preview or for production—it goes through a sequence of phases:

### 1. Load Phase

Docusaurus first reads your configuration and loads every plugin and theme you have enabled. During this phase, each plugin reports what content it is responsible for and what routes it will provide. The core collects this information into a single unified map of the entire site.

### 2. Route Phase

Once all content sources are known, Docusaurus computes the complete set of pages. It identifies every documentation page, every blog post, every standalone page, and any dynamically generated routes. A single URL is assigned to each page based on the plugin's settings and the overall site configuration.

### 3. Render Phase

In the final phase, each route is converted into actual output files. The core walks through every page, applies the appropriate theme layout, injects the content, and writes the result to disk as static files. The end result is a complete folder of HTML, CSS, JavaScript, and assets that can be hosted anywhere.

This phased approach keeps the system orderly: first figure out *what exists*, then *where it lives*, then *what it looks like*.

---

## How Plugins Extend Functionality

Plugins conform to a consistent pattern, regardless of what they do. Each plugin describes:

- **What content it provides:** which pages, posts, or documents it contributes
- **Which routes it owns:** the URLs where that content appears
- **What data it exposes:** information other parts of the site can look up
- **Which theme to apply:** how its content should be presented

This uniform contract means plugins compose cleanly. A search plugin can inspect content produced by the documentation plugin. A theme can style pages contributed by any plugin. The core treats every plugin equally, routing data between them without needing to know the specifics.

When you add a new plugin, you are not modifying the core. You are attaching a new module that speaks the same protocol as everything else. This makes the system both predictable and endlessly expandable.

---

## The Swizzle Mechanism for Theme Customization

Themes are packaged with their own layouts and components. But every site has unique needs. Docusaurus solves this with a feature called **swizzling**.

Swizzling is the process of taking a component that ships inside a theme and creating a modified copy inside your own project. Once you have swizzled a component, your copy overrides the original. You can then edit it freely without touching the theme itself.

There are two degrees of swizzling:

- **Wrapping** — you keep the original component but add your own logic around it. Useful when you want to enhance behavior without reimplementing it.
- **Ejecting** — you take full ownership of the component's code. Useful when you need to change its fundamental behavior or appearance.

A **swizzle test workflow** typically looks like this: you identify the component you want to change, swizzle it, run the build, and verify that your customized version appears in the output. If the result is not what you expected, you can safely remove your swizzled copy and the site reverts to the theme's original component—your modifications never alter the theme itself.

This mechanism provides a clean, reversible path for deep customization without forking entire themes.

---

## Putting It All Together

The modular architecture of Docusaurus can be summarized as:

- **Core** provides the stable foundation
- **Plugins** contribute content and capabilities
- **Themes** govern appearance
- **Presets** bundle plugins and themes for convenience
- **The build lifecycle** moves from loading to routing to rendering
- **Swizzling** offers a safe way to customize theme components

Every extension point follows the same principle: *you change one piece without breaking the rest*. This is what makes Docusaurus approachable for beginners—the classic preset does the heavy lifting—and powerful for advanced teams who need fine-grained control.
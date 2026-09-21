# How to Customize the Homepage and Feature Showcase

This guide helps you rebrand the landing page by changing the hero area, the call-to-action button, the three feature cards, and the general look and feel.

---

## What You Can Change

Your homepage includes:

- A large hero band at the top with your site name, tagline, and a button.
- Three feature cards below the hero, each with a title, an illustration, and a short description.
- Styling that controls colors, spacing, and image sizes.

You can change all of these without rebuilding the whole site.

---

## Change the Hero Title and Tagline

The hero title and tagline come from your site-wide settings, not from the homepage itself.

**Current defaults:**

- Title: `My Site`
- Tagline: `Dinosaurs are cool`

**To customize:**

1. Open your site’s main configuration file.
2. Find the setting that stores the site title.
3. Replace `My Site` with your product or company name.
4. Find the setting that stores the tagline.
5. Replace `Dinosaurs are cool` with a short sentence that describes your product.
6. Save the file.

The homepage hero will immediately use the new title and tagline.

> The page title shown in the browser tab is also based on this same site title setting.

---

## Change the Call-to-Action Button

The hero area contains a single call-to-action button.

**Default button text:**

`Docusaurus Tutorial - 5min ⏱️`

**Default button destination:**

The introduction page of the documentation.

**To customize:**

1. Open the homepage content file.
2. Find the call-to-action button text.
3. Replace the default text with your own, such as `Get Started` or `Learn More`.
4. Find the button destination setting.
5. Change the destination to the page you want visitors to see first, such as your main documentation page.
6. Save the file.

---

## Change the Three Feature Cards

The homepage displays three feature cards. Each card has:

- A title
- An illustration
- A short description

The default cards are:

| Title | Default Description |
| --- | --- |
| Easy to Use | Explains that the site is designed to be installed and used quickly. |
| Focus on What Matters | Explains that users can focus on their content while the site handles the rest. |
| Powered by React | Explains that the website layout can be extended and customized. |

**To edit a card:**

1. Open the homepage feature content file.
2. Find the card you want to change.
3. Update the title, description, or illustration to match your brand.
4. Save the file.

**To change an illustration:**

1. Upload your own illustration file to your site’s images folder.
2. In the feature card, replace the current illustration reference with the name of your new image.
3. Save the file.

---

## Add a New Feature Card

You can add a fourth card, a fifth card, or as many as you need.

**To add a card:**

1. Open the homepage feature content file.
2. Locate the list of existing feature cards.
3. Add a new card entry after the last existing card.
4. Give the new card:
   - A title
   - An illustration reference
   - A short description
5. Save the file.

The homepage will automatically display the new card alongside the existing ones.

---

## Remove a Feature Card

You can also remove a card if you want a simpler homepage.

**To remove a card:**

1. Open the homepage feature content file.
2. Find the card you no longer want.
3. Delete that card entry from the list.
4. Save the file.

The remaining cards will automatically adjust to fill the available space.

---

## Adjust Colors, Spacing, and Image Size

The homepage appearance is controlled by style settings separate from the content.

**Common styling changes you can make:**

- Change the background color of the hero band.
- Change the spacing around the call-to-action button.
- Change the size of the feature card illustrations.
- Change the spacing between feature cards.

**Where to change these:**

1. Open the homepage style file.
2. Find the setting for the hero banner background.
3. Adjust the color value to match your brand.
4. Find the setting for the button spacing.
5. Adjust the spacing value if needed.
6. Find the setting for the feature illustration size.
7. Increase or decrease the image size as desired.
8. Save the file.

There is also a separate style file for the feature section, where you can adjust how the three cards sit together.

---

## Quick Rebranding Checklist

Use this checklist to fully rebrand the landing page:

- [ ] Change the site title from `My Site` to your product name.
- [ ] Change the tagline from `Dinosaurs are cool` to your own tagline.
- [ ] Update the call-to-action button text.
- [ ] Update the call-to-action button destination.
- [ ] Update the title, description, and illustration for each feature card.
- [ ] Add any new feature cards.
- [ ] Remove any feature cards you do not need.
- [ ] Adjust the hero background color to your brand color.
- [ ] Adjust the feature illustration size if needed.
- [ ] Review the homepage and confirm everything matches your brand.

---

## Troubleshooting Tips

- If your title or tagline does not change, make sure you edited the site settings file, not only the homepage content.
- If a new feature card does not appear, confirm it was added to the list of cards and saved.
- If an illustration is missing, check that the image file name matches exactly, including the extension.
- If the homepage looks uneven after adding or removing cards, review the feature section spacing settings.
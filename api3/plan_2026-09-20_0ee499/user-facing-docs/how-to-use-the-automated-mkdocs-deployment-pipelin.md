# How to Use the Automated MkDocs Deployment Pipeline

This guide explains what happens automatically when you update the documentation site, and what to do if a publish fails.

## What This Pipeline Does

Your documentation site is built and published automatically. Whenever you save changes to the main branch of the documentation project, the publishing system:

- Takes the current documentation source files
- Builds them into a finished website
- Publishes the finished site to your public documentation URL

You do not need to run any install or build commands yourself.

## What Happens on Each Push

### 1. Publishing Starts When Changes Reach Main

The process is triggered only when changes are pushed to the main branch. Work saved to other branches does not trigger a public update.

### 2. Security Permissions Are Applied

The system starts each run with limited, specific access:

- It can read your documentation content
- It can update the public site storage
- It receives a temporary identity for secure deployment

No broad or permanent access keys are used.

### 3. The Latest Content Is Checked Out

The publishing system opens a clean workspace and retrieves the latest copy of all documentation files from the main branch.

### 4. A Python 3.12 Environment Is Prepared

Because the site is built with MkDocs, the system creates a fresh runtime with Python 3.12 installed.

### 5. Dependencies Are Installed

The system upgrades its package installer and then installs two documentation tools:

- MkDocs — the site builder
- The Material theme — the visual design used by the site

These are installed fresh on every publish.

### 6. The Site Is Built

The system runs the documentation build process. It converts your text-based documentation content into a finished website, including navigation, search, and styling. The result is a compiled site ready to publish.

If any page has invalid formatting, broken navigation, or missing content, this step can fail.

### 7. GitHub Pages Settings Are Prepared

The publishing system prepares the hosting configuration so the built site will be served correctly.

### 8. The Built Site Is Uploaded

The compiled site files are packaged and uploaded as a temporary artifact, ready for the deployment step.

### 9. The Site Is Deployed

A second job takes the uploaded artifact and publishes it to a protected environment called GitHub Pages. This is the final step that makes the site live.

### 10. The Public URL Is Recorded

After deployment, the system records the public address of the deployed site. You can see this URL in the deployment summary for the run.

## Concurrency Control

Only one publication can run at a time. If you push changes while an older publication is still running, the older run is cancelled and the newer run takes over. This prevents two versions of the site from being published at the same time.

The final published site always matches the most recent accepted push.

## How to Re-run a Failed Deployment

If a publish fails, the live site remains at its last successful version. Fix the cause first, then re-run the failed publication:

1. Open your documentation project in its web interface.
2. Select **Actions** from the top navigation.
3. Find the failed run for the documentation publishing workflow.
4. Select **Re-run jobs**, then choose **Re-run all jobs**.

After re-running, watch the run to confirm it completes successfully.

## Troubleshooting a Failed Publish

### Check Recent Content Changes

Most failures are caused by a recent edit. If a page was renamed, removed, or linked incorrectly, the build can fail. Review your most recent changes:

- Make sure every page in the site navigation still has a matching source page.
- Look for broken internal links between documentation pages.
- Check that section headings and list formatting are valid.

### Check the Build Step

If the run fails during the build step, the error message usually identifies the page or line causing the problem. Read the failed step log to find that page.

### Be Aware of Package Installation Limits

Your project includes a list of required packages, but the current automatic publishing process installs only MkDocs and the Material theme directly. If you add optional formatting extensions or custom packages, they may not be installed automatically. Contact the project maintainers before relying on new packages.

### If the Deployment Step Fails

Failures after a successful build are often temporary hosting issues. Re-run the failed deployment as described above. If it continues to fail, check whether the protected GitHub Pages environment is enabled for your project.

## What You Need to Do

For normal documentation updates:

1. Make your edits in the documentation project.
2. Commit the changes to the main branch.
3. The publishing process runs automatically.
4. Wait a few minutes and then refresh your public documentation site to see the new content.
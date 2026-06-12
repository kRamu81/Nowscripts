# Nowscripts

Static website code and assets for nowscripts.com.

---

## Technical Writer Guide: How to Add Content

This is a **static HTML website** (flat-file structure without a database or dynamic WordPress backend). All pages are directories containing an `index.html` file. Any new article, event, or newsletter must be created manually on the filesystem, linked in the appropriate indices, and pushed to GitHub.

---

### Table of Contents
1. [Adding a News Article](#1-adding-a-news-article)
2. [Adding an Event](#2-adding-an-event)
3. [Adding a Newsletter Issue](#3-adding-a-newsletter-issue)
4. [Uploading and Referencing Images](#4-uploading-and-referencing-images)
5. [Publishing Your Changes to GitHub](#5-publishing-your-changes-to-github)

---

### 1. Adding a News Article

#### Step 1.1: Create the Article Directory and File
1. Under the root folder `nowscripts.com/`, create a new folder named using lowercase letters and hyphens for the URL slug:
   `nowscripts.com/your-article-slug/`
2. Create a file named `index.html` inside this new directory:
   `nowscripts.com/your-article-slug/index.html`
3. Copy the entire HTML structure from an existing article page to use as a template, for example:
   [exclusive-servicenow-lays-off-hundreds-of-employees-in-restructuring-effort/index.html](file:///e:/NQT/tools/nowscripts.com/exclusive-servicenow-lays-off-hundreds-of-employees-in-restructuring-effort/index.html)

#### Step 1.2: Edit Page Content and Metadata
Open the new `index.html` file and update:
* **SEO Metadata** (inside `<head>`):
  * `<title>` tag (e.g., `<title>Your Article Title - NowScripts</title>`)
  * `<meta name="description" ...>` tag
  * `<link rel="canonical" href="https://nowscripts.com/your-article-slug/" />`
  * OpenGraph tags (`og:title`, `og:description`, `og:url`, `og:image`)
* **Article Header**:
  * Category name and link (`/servicenow-news/`)
  * Article Title (in the `<h1>` element)
  * Author name and link
  * Publish Date (e.g. `June 12, 2026`)
  * Featured Image background style (e.g., `background-image:url(../wp-content/uploads/2026/06/your-image.webp)`)
* **Article Body**:
  * Replace the text blocks inside the `<div class="entry-content">` with your article markup (using standard `<p>`, `<h2>`, `<h3>` tags).

#### Step 1.3: Link the Article on Listing Pages
To make sure readers can find your new article, you must add it to the listings:
1. **Category Page**: Open [servicenow-news/index.html](file:///e:/NQT/tools/nowscripts.com/servicenow-news/index.html).
   * Find the `<article>` list container.
   * Duplicate one of the existing `<article>` elements and place it at the **top** of the list (so it renders as the newest post).
   * Update the `href` link, category text, title, author name, date, and featured image URL to point to your new folder.
2. **Homepage**: Open [index.html](file:///e:/NQT/tools/nowscripts.com/index.html) at the root.
   * Locate the "Latest Articles" grid section.
   * Insert your new article link block at the top of the grid and shift or remove the oldest item to maintain layout symmetry.

---

### 2. Adding an Event

#### Step 2.1: Create the Event Directory and File
1. Under the root folder `nowscripts.com/`, create a new folder for your event slug:
   `nowscripts.com/your-event-slug/`
2. Create an `index.html` file inside this folder:
   `nowscripts.com/your-event-slug/index.html`
3. Copy the structure from an existing event page as your starting template.

#### Step 2.2: Link the Event on the Events Directory
1. Open the events page: [servicenow-events/index.html](file:///e:/NQT/tools/nowscripts.com/servicenow-events/index.html).
2. Find the event list grid or block section.
3. Add a new event card linking to `../your-event-slug/index.html` with the event title, banner, location, and dates.

---

### 3. Adding a Newsletter Issue

#### Step 3.1: Create the Newsletter Directory
1. Create a folder under `nowscripts.com/` named with the newsletter issue identifier:
   `nowscripts.com/newsletter-issue-name/`
2. Create an `index.html` inside it.

#### Step 3.2: Link the Newsletter Issue
1. Open the newsletter directory page: [newsletters/index.html](file:///e:/NQT/tools/nowscripts.com/newsletters/index.html).
2. Locate the newsletter list block.
3. Append a new list item linking to the new issue: `<a href="../newsletter-issue-name/index.html">Issue Name</a>`.

---

### 4. Uploading and Referencing Images

* All content-related images (featured images, article screenshots) must be saved inside the uploads folder:
  `nowscripts.com/wp-content/uploads/2026/[current-month-number]/` (e.g. `/06/` or `/07/`).
* **Format**: Keep images optimized for web speed. Prefer `.webp` or highly compressed `.png`/`.jpg` formats.
* **Paths**: When referencing the image from your new page, use relative paths. For example, if your article is in `/your-article-slug/index.html`, point to your image like this:
  `../wp-content/uploads/2026/06/your-image.webp`

---

### 5. Publishing Your Changes to GitHub

Once you have added the files and updated the indices locally, run the following Git commands to push your changes live:

```bash
# Stage the new directory and updated HTML lists
git add .

# Commit your changes
git commit -m "Publish new article: Your Article Title"

# Push the changes to GitHub
git push origin main
```

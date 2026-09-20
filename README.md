# AP Psychology course site

Static site of student-facing resources for AP Psychology.
No build step, no dependencies, no JavaScript frameworks. Every page is plain HTML and opens
correctly by double-clicking it on your own computer.

## Publishing this to GitHub Pages

Do this once. After that, updating the site is just editing a file and pushing.

1. Go to github.com and create a new repository named `ap-psychology`. Set it to **Public**
   (GitHub Pages on free accounts requires public). Do not add a README, since this folder has one.
2. Upload this entire folder. The easiest route with no command line: on the new empty repo page,
   click **uploading an existing file**, then drag the *contents* of this folder in
   (`index.html`, `assets`, `unit-0`, and the rest). Commit.
3. In the repo, go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
4. Wait about a minute, then reload the Settings → Pages screen. It will show your live URL:
   `https://YOUR-USERNAME.github.io/ap-psychology/`
5. Open that URL and click through to the research methods page to confirm it works.

Link that URL from your Canvas modules.

## Updating a page later

Editing in the browser is fine for small changes: open the file in GitHub, click the pencil icon,
edit, commit. The live site updates within a minute. Every edit is kept in the repo history, so
you can compare against last year's version or roll back a change that did not work.

## Adding a new resource

1. Drop the HTML file into the right unit folder, for example `unit-2/memory-practice.html`.
2. Open that unit's `index.html` and copy an existing `<a class="resource">` block, changing the
   filename, title, and description.
3. On `index.html` at the site root, update that unit's card so it no longer says
   "Resources coming soon".

## Search visibility

Every page carries `<meta name="robots" content="noindex, nofollow">`, which is what actually keeps
these pages out of Google. The `robots.txt` file is included for completeness, but be aware that
search engines only read `robots.txt` at a domain root, so on a project site like this one
(`username.github.io/ap-psychology/`) it is ignored. The meta tag is doing the real work.

If you later decide you want the site discoverable, delete that meta tag line from each page.

## Structure

```
index.html            course home, unit cards
assets/site.css       all styling for the site
unit-0/index.html     unit landing page
unit-0/research-methods.html
unit-1/ ... unit-5/   same pattern
.nojekyll             tells GitHub Pages to serve files as-is
```

Resource pages such as `research-methods.html` are self-contained and carry their own styles, so
they do not depend on `assets/site.css`. That is deliberate: it means you can also hand one of them
out as a standalone file or upload it to Canvas without anything breaking.

# Personal website — Dr.-Ing. Sarah Ouerghemmi

A static site in two languages. English at the root, German in the `de/` folder.
No build step, no dependencies. Open `index.html` in a browser to see it.

## Files

```
index.html         Home (English)
research.html      Research
projects.html      Projects
cv.html            CV: experience, skills, education, awards, contact
404.html           Shown when a visitor hits a URL that does not exist
de/                The same five pages in German
img/portrait.jpg   Your photo (square)
img/favicon.svg    The icon in the browser tab
CV_Sarah_Ouerghemmi.pdf   Linked from the download buttons
robots.txt         Lets search engines index the site
sitemap.xml        Lists both language versions
.nojekyll          Tells GitHub Pages to serve the files as they are
```

Keep the structure as it is. The German pages reach the images and the CV with
`../`, so moving them breaks those links.

## The language switch

Every page has a button in the header that jumps to the same page in the other
language: `research.html` goes to `de/research.html` and back. Each page also
declares the other language in its `<head>` with `hreflang`, so Google shows a
German visitor the German version.

## Before you publish: one find-and-replace

The placeholder `https://YOUR-USERNAME.github.io/` appears in every HTML file,
in `robots.txt` and in `sitemap.xml`. Replace it with your real address. It is
used for the preview card when someone shares a link on LinkedIn, and for search
engines. The site works without this; only the share cards suffer.

## Publishing on GitHub Pages (free)

1. Create a repository. Named `YOUR-USERNAME.github.io`, the site lives at
   `https://YOUR-USERNAME.github.io`. Any other name puts it in a subfolder.
2. Upload everything from this folder, including `img` and `de`.
3. Settings, then Pages. Source: "Deploy from a branch", branch `main`,
   folder `/ (root)`. Save.
4. Wait a minute and reload. The address appears at the top of that page.

### Your own domain

Add it under Settings, Pages, "Custom domain", then at your registrar create a
CNAME record pointing to `YOUR-USERNAME.github.io`. Tick "Enforce HTTPS".

## Editing

Plain HTML with the CSS inside each file. Colours: the `--accent` value near the
top of the `<style>` block. Photo: replace `img/portrait.jpg`.

Content lives between the `<main>` tags. A publication looks like this:

```html
<div class="pub">
  <div class="year">2025</div>
  <div>
    <p class="title">Title of the paper</p>
    <p class="authors"><strong>S. Ouerghemmi</strong>, co-authors</p>
    <p class="venue">Journal or conference</p>
    <p class="links"><a href="https://doi.org/...">DOI</a></p>
  </div>
</div>
```

Copy one, change the text. Projects use `<div class="proj">` and jobs use
`<div class="entry">` the same way. Change both languages when you add something,
or the two versions drift apart.

Note that the pages were generated from a script, so the CSS is duplicated in
each file. If the site keeps growing, MkDocs Material builds pages from Markdown,
handles two languages, and gives you real search across all of them.

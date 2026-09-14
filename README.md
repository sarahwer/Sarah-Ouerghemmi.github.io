# Personal website — Dr.-Ing. Sarah Ouerghemmi

A static site. Three pages, no build step, no dependencies. Open `index.html`
in a browser to see it exactly as it will look online.

## Files

```
index.html        Profile: about, experience, skills, education, awards, contact
research.html     Research: wake-up receivers, topics, publications, teaching
projects.html     Projects: FUBE, WakeUp-Receiver, CONCENTRATE, earlier work
404.html          Shown when a visitor hits a URL that does not exist
img/portrait.jpg  Your photo (square, 520x520)
img/favicon.svg   The little icon in the browser tab
CV_Sarah_Ouerghemmi.pdf   Linked from the "Download CV" button
robots.txt        Lets search engines index the site
sitemap.xml       Lists the three pages for search engines
.nojekyll         Tells GitHub Pages to serve the files as they are
README.md         This file
```

Keep everything in one folder. The links between pages are relative.

## Before you publish: one find-and-replace

Four files contain the placeholder `https://YOUR-USERNAME.github.io/`:
`index.html`, `research.html`, `projects.html`, `404.html`, `robots.txt`,
`sitemap.xml`. Replace it with your real address once you know it. It is used
for the preview card that appears when someone shares a link on LinkedIn, and
for search engines. The site works without doing this; the share cards just
will not show your photo.

## Publishing on GitHub Pages (free)

1. Create a free account at github.com if you do not have one.
2. Create a new repository. If you name it `YOUR-USERNAME.github.io`, the site
   lives at `https://YOUR-USERNAME.github.io`. Any other name puts it at
   `https://YOUR-USERNAME.github.io/repository-name/`. Make it public.
3. On the repository page choose "uploading an existing file", then drag in
   everything from this folder, including the `img` folder. Commit.
4. Go to Settings, then Pages in the left menu. Under "Build and deployment"
   set Source to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
5. Wait a minute or two and reload. The address appears at the top of that page.

To change anything later, edit the file on GitHub or upload a new version. The
site updates within a minute.

### Your own domain

If you buy a domain (for example `sarah-ouerghemmi.de`), add it under
Settings, Pages, "Custom domain", and at your domain registrar create a CNAME
record pointing to `YOUR-USERNAME.github.io`. Tick "Enforce HTTPS" once it is
verified.

## Other hosts

The same files work anywhere that serves static sites. Netlify and Cloudflare
Pages both let you drag the folder onto their dashboard and are free for this.

## Editing

Everything is plain HTML with the CSS inside each file. To change the colours,
edit the `--accent` value near the top of the `<style>` block in each page.
To swap your photo, replace `img/portrait.jpg` with another square image.

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

Copy one, change the text, done. Projects use `<div class="proj">` and jobs use
`<div class="entry">` the same way.

If the site grows past a handful of pages, consider moving it to MkDocs
Material, which builds pages from Markdown and adds real search across all of
them.

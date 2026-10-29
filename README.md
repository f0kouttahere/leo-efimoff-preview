# Leo Efimoff — portfolio site

A one-page portfolio for Leo Efimoff, a sculptor based in Russia. The site will be used to represent and sell his work in the US, North America and possibly worldwide.

It's a static site with no build step and no dependencies: plain HTML, CSS and JS. Open `index.html` in a browser, or host the folder anywhere that serves static files (for example GitHub Pages or Netlify).

## Files

- `index.html`: the whole site, including the page, styles, script and all EN/ES interface text (the `TEXT` object in the script).
- `about.html`: separate About page (bio, three studio photos).
- `contacts.html`: separate Contacts page — contact form, Instagram and email. Photo: `images/contacts/leo-portrait-bw.webp` (portrait with tubular sculptures; source `IMG_3369.jpg`, 1170x1455).
- `works.js`: the gallery list in display order (currently newest first). This is the only file you edit to add titles or reorder works.
- `images/`: two WebP files per work. `work-NN.webp` is 1440px wide and used on desktop and in the full-screen view. `work-NN-720.webp` is 720px wide and used on phones and in the grid. All 40 photos are portrait (3:4 to 4:5).

## Design decisions (agreed with the client)

- Very minimal, white background, Inter Light. No captions in the grid.
- Grid columns: 4 on screens 1400px and wider, 3 on laptops, 2 on screens up to 760px. The grid crops photos to 39:50, which trims at most about 3% from any edge. The full-screen view is never cropped.
- Full-screen view: prev/next arrows, arrow keys, Esc to close, swipe on phones, and an "N / 40" counter.
- **A work's title appears only in the full-screen view, directly under the photo.** A smaller grey details line (material, size) goes under the title. If a work has no title, nothing is shown.
- Languages: English (default) and Spanish, switched with EN / ES in the header. Russian was deliberately removed. Visitors whose browser is set to Spanish see Spanish first.

## Adding titles

In `works.js`, change an entry from `{ id: "03" }` to:

```js
{ id: "03", title: { en: "Title", es: "Título" }, meta: { en: "Carrara marble, 180 cm", es: "Mármol de Carrara, 180 cm" } },
```

`meta` is optional. The number in `id` matches the image file names and the numbered contact sheets.

## Still to do

1. **Real titles for all 40 works.** They are in the captions of Leo's Instagram posts (@levefimov_official, in Russian). `handoff/leo-efimoff-works.csv` links each work number to its Instagram post. These links were worked out from the post IDs in the original export's file names, so spot-check a few. The CSV also has empty columns for title, material, dimensions, year and price. Translate the titles into English and Spanish.
2. **About text and intro line are placeholders** (in the `TEXT` object in `index.html`). The About text currently calls him a "Russian artist". The client hasn't decided whether to keep that, so confirm before publishing. Ideally use a real bio.
3. **Contact email is a placeholder** on `contacts.html` (`hello@example.com`). Instagram is wired to the real handle `@leoefimoff`. The form has no backend: it validates and tells the visitor nothing was sent, so it needs a mail service (Formspree, Netlify Forms, or just a `mailto:` link) before publishing.
4. **Order of works:** the four outdoor garden and courtyard renders (works 02–05) currently lead the grid. It was suggested to the client that the grid open with a studio shot instead. Not decided.
5. **Hosting:** the site isn't online yet.
6. The folder is still named `lev-efimov` (an older spelling). Rename it to `leo-efimoff` before hosting if it will appear in the URL.

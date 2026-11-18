# ansocho.github.io

Personal homepage of Andreas Sochopoulos: plain Jekyll, built by GitHub Pages
directly from `main` (no Actions, no npm, no Docker).

```
_config.yml              site title, description, GA id, social links
_data/publications.yml   all papers (newest first)
_data/news.yml           news items (newest first)
_data/socials.yml        email / GitHub / LinkedIn / Scholar
_layouts/default.html    the only layout
_includes/               head (SEO + GA), nav, footer, socials, news, publication, person JSON-LD
assets/css/style.css     the only stylesheet (light + dark)
index.md                 About + News + Selected Publications
publications.md, news.md, cv.html (/cv -> PDF), 404.html, robots.txt
```

## Add a news item

Add an entry at the top of `_data/news.yml`:

```yaml
- date: 2027-01-15
  text: >-
    Our paper, <a href="https://...">Title</a>, has been accepted at ...!
```

The homepage shows the 5 most recent; `/news/` shows all. Future dates are shown too.

## Add a paper

Add an entry at the top of `_data/publications.yml` (copy an existing one).
Your name is bolded automatically. Set `selected: true` to show it on the homepage.

For the preview, convert the GIF to a small MP4 plus a poster frame and put both
in `assets/img/publication_preview/`:

```sh
cd assets/img/publication_preview
ffmpeg -i new.gif -movflags +faststart -pix_fmt yuv420p -vf "scale='min(480,iw)':-2" -c:v libx264 -crf 26 -an new.mp4
ffmpeg -i new.gif -vf "scale='min(480,iw)':-2" -frames:v 1 -q:v 4 new.jpg
```

then set `preview: new.mp4`. (A plain `.png`/`.jpg`/`.gif` also works.)

## Update the CV

Overwrite `assets/pdf/CV_AS.pdf`. If you rename the file, update the path in `cv.html`.

## Run locally

```sh
bundle install
bundle exec jekyll serve      # http://localhost:4000
```

Google Analytics is only included in production builds (`JEKYLL_ENV=production`, which GitHub Pages uses).

## Deployment and Google (one-time)

1. **Settings → Pages**: Source = "Deploy from a branch", branch `main`, folder `/ (root)`.
   The old `gh-pages` branch can be deleted once the new site is live.
2. **Google Search Console**: add a URL-prefix property `https://ansocho.github.io/`, choose the
   HTML-tag method, and paste the code into `_config.yml`:
   ```yaml
   webmaster_verifications:
     google: YOUR-CODE
   ```
   Push, then click Verify.
3. Submit `sitemap.xml` in Search Console, then URL Inspection on the homepage → **Request indexing**.
4. Link this site from Google Scholar, LinkedIn, the GitHub profile and the University of Edinburgh
   lab page. Off-site links matter as much as on-page SEO.

Note: `/cot-policy/` and `/otql-flow/` are separate GitHub Pages project repos served on this
domain; don't create files under those paths here.

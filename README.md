# amirrsyed.github.io

[amirrsyed.github.io](https://amirrsyed.github.io/) — built with Jekyll on GitHub Pages.

## Publishing an essay

1. On the repo's main page, click **Add file → Create new file**.
2. Name it `_posts/YYYY-MM-DD-short-title.md`, for example `_posts/2026-10-05-on-markets.md`.
   The date in the name is the publish date; the rest becomes the URL (`/writing/on-markets/`).
3. Paste in this header, then your essay below it (a template is in `_drafts/essay-template.md`):

   ```
   ---
   title: "On Markets"
   description: "Optional one-sentence summary for link previews."
   ---
   ```

4. Click **Commit changes**. The site rebuilds in about a minute. The essay appears on
   `/writing/`, on the homepage, in the RSS feed (`/feed.xml`), and in the sitemap automatically.

A post dated in the future won't appear until that date (after the next commit).
## Updating /now

Edit `now.html` and write below the `<h1>Now</h1>` line.

## Editing

To edit or unpublish, edit or delete the file in `_posts/`.
Files in `_drafts/` are never published.

## Structure

- `_layouts/default.html` — shared header, footer, and page metadata
- `_layouts/post.html` — essay page
- `assets/style.css` — all styling
- `_config.yml` — site settings (change `url` when using a custom domain)

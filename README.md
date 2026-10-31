# amirsyed.xyz

[amirsyed.xyz](https://amirsyed.xyz/) — built with Jekyll on GitHub Pages. Every change merged
into `main` is live in about a minute.

## Publishing an essay

1. On the repo's main page, click **Add file → Create new file** (or press `.` to open the
   browser editor).
2. Name it `_posts/YYYY-MM-DD-short-title.md`, for example `_posts/2026-10-05-on-markets.md`.
   The date in the name is the publish date; the rest becomes the URL (`/writing/on-markets/`).
3. Paste in this header, then your essay below it (a template is in `_drafts/essay-template.md`):

   ```
   ---
   title: "On Markets"
   description: "Optional one-sentence summary for link previews."
   ---
   ```

4. Click **Commit changes**. The essay appears on `/writing/`, on the homepage, in the RSS feed
   (`/feed.xml`), and in the sitemap automatically.

**Scheduling:** give the file a future date and it goes live on that morning. The
*Daily rebuild* workflow rebuilds the site every day at about 6 am Eastern.

**Reviewing first:** on the commit screen, choose **Create a new branch … and start a pull
request** instead of committing to `main`. The post goes live when you merge the pull request.

## Updating Investing Theses

Edit `theses.html` and write below the `<h1>Investing Theses</h1>` line. (The old `/now` address
redirects here.)

## Editing

To edit or unpublish an essay, edit or delete its file in `_posts/`.
Files in `_drafts/` are never published.

## Design and code changes

Make design or code changes on a branch and open a pull request rather than committing to `main`.
The **Build and link check** workflow builds the site with the same Jekyll version GitHub Pages
uses and checks for broken internal links and images. A green check means it's safe to merge;
a red X means something would break — open the check's log to see what.

To preview locally (needs Ruby):

```
bundle install
bundle exec jekyll serve
```

then open http://localhost:4000.

## Automation

- `.github/workflows/daily-rebuild.yml` — rebuilds the site daily so future-dated posts publish
  on time. Run it by hand from **Actions → Daily rebuild → Run workflow**. GitHub pauses scheduled
  workflows after 60 days with no commits; re-enable it from the Actions tab if that happens.
- `.github/workflows/check.yml` — build and link check on every pull request and push to `main`.

## Structure

- `_layouts/default.html` — shared header, navigation, footer, and page metadata
- `_layouts/post.html` — essay page
- `assets/style.css` — all styling
- `_config.yml` — site settings (`url` is the live domain)
- `CNAME` — the custom domain; don't delete it
- `Gemfile` — build tools for the check and local preview (not used by GitHub Pages itself)

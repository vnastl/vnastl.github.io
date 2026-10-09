# vnastl.github.io

Personal website, built with [Jekyll](https://jekyllrb.com/). Everything you edit is a Markdown file:

| What you want to change | File |
|---|---|
| Bio | `about.md` (text below the front matter; `affiliation:` in the front matter) |
| Add a news item | new file `_news/YYYY-slug.md` with `date:` and one paragraph |
| Add a talk | new file `_talks/YYYY-slug.md` with `date:`, `type:`, `event:`, `place:` (optional `title:`, `link:`) |
| Add or change a paper | `_publications/YYYY-slug.md`; its figure in `assets/img/publications/` |
| CV page | `cv.md` (publications and talks are filled in from their folders) |
| CV PDF | `latex/cv.tex`, then `latexmk -pdf -cd latex/cv.tex && cp latex/cv.pdf assets/cv.pdf` |
| Name, email, Google Scholar / GitHub / LinkedIn ids, number of visible news items | `_config.yml` |
| Colours, font, spacing | `assets/css/style.css` (colours in the `:root` block at the top) |
| Logo, photo | `assets/img/logo.svg`, `assets/img/profile.jpg` |

Layouts (`_layouts/`) and includes (`_includes/`) are the theme; they do not need touching for day-to-day updates.

## Preview locally

Needs Ruby 3.4 (`brew install ruby@3.4`, then put `/opt/homebrew/opt/ruby@3.4/bin` first on your `PATH`).

```
bundle install --path vendor/bundle
bundle exec jekyll serve
```

Then open http://localhost:4000.

## Deploy

Push to `main`. GitHub Actions builds the site and publishes it to the `gh-pages` branch (see `.github/workflows/deploy.yml`). The workflow also rebuilds once a week so that the "upcoming" marker on talks stays current.

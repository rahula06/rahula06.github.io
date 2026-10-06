# Rahul Arvind — academic website

A small Jekyll website for GitHub Pages, with Home, Publications, and Blog pages. No custom backend or paid theme is needed. Publication years indicate first preprint dates; journal details are listed separately.

## Preview the design

Open `PREVIEW.html` in a browser. It is a self-contained design preview with working page navigation, built from the same content and CSS as the site. It is excluded from the published site. The actual site is built by Jekyll.

## Publish on GitHub Pages

1. Create a **public** GitHub repository named `YOUR-USERNAME.github.io`, replacing YOUR-USERNAME with your GitHub username in lowercase. If that repository already exists, edit the existing site deliberately instead of overwriting its files.
2. Upload the **contents** of this folder to the repository root, including the underscore-prefixed folders. Do not upload just the ZIP or an enclosing folder.
3. Edit `_config.yml`: set `url` to `https://YOUR-USERNAME.github.io`. Leave `baseurl: ""`. Optionally fill in `email`, `github_url`, and `scholar_url`; blank links are hidden.
4. Review the bio in `index.html` and the publication entries in `_data/publications.yml`. Add your current affiliation to the bio if desired. The four entries were sourced from public records; confirm completeness and preferred journal citations before publishing.
5. In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then **main** and **/(root)**. Save.
6. Check the repository's **Actions** tab for the Pages build. Once it succeeds, visit `https://YOUR-USERNAME.github.io`. Publication may take several minutes.

Do not add a `.nojekyll` file: this site needs Jekyll to render its templates.

For a project repository instead, set `url` to `https://YOUR-USERNAME.github.io` and `baseurl` to `/REPOSITORY-NAME`; the templates use relative_url for internal links.

## Add a publication

Edit `_data/publications.yml`. Copy an existing entry, update its details, and place it in newest-first order. Quote titles and arXiv IDs. The first two entries appear on the home page. `doi` is optional. Only provide the identifier, such as `10.1103/PhysRevResearch.7.013105`, not a full URL.

## Write a blog post

Create a file in `_posts` named `YYYY-MM-DD-short-title.md`, for example `2026-10-06-randomness.md`. You can do this directly in GitHub with **Add file → Create new file**.

Start it with:

```yaml
---
title: "Your post title"
description: "A one-sentence description."
math: true
---
```

Then write the post in Markdown. `math: true` enables MathJax from a CDN; use `$...$` for inline mathematics and `$$...$$` for display mathematics. Omit `math` if unnecessary. Committing the file publishes it on the next successful Pages build. Posts dated in the future stay unpublished by default.

`_drafts/first-post.md` contains an unpublished template. Move and rename it into `_posts` only once it contains your own writing. Drafts are omitted by Jekyll unless you explicitly build with `--drafts`; a public source repository still exposes their source text, so keep private writing outside the repository.

## Optional local development

With Ruby and Bundler installed:

```sh
bundle install
bundle exec jekyll serve
```

Visit `http://localhost:4000`. Use `bundle exec jekyll serve --drafts` to preview drafts. Restart Jekyll after editing `_config.yml`.

## Files to edit

| File | Purpose |
| --- | --- |
| `index.html` | Home page and biography |
| `_data/publications.yml` | Publication list |
| `_posts/YYYY-MM-DD-title.md` | Published blog post |
| `_config.yml` | Site URL and contact links |
| `assets/style.css` | Colors, typography, and layout |

## Validation

Publication data, YAML front matter, and template references were checked locally. The standalone preview is provided for browser review. Browser automation and a full Jekyll build could not run in the preparation environment because a browser and Ruby were unavailable; verify the preview and first GitHub Pages build before treating deployment as complete.

## Official guides

- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll

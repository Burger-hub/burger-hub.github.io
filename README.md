# Academic homepage

Source for https://burger-hub.github.io/, based on AcademicPages (Jekyll).

## Fill in your information

You can edit these files directly on GitHub: open the file, click the pencil,
make changes, then choose **Commit changes** on the master branch.

| Information | File |
| --- | --- |
| Name, title, affiliation, email, photo and profile links | `_config.yml` |
| Biography, research interests and education | `_pages/about.md` |
| Navigation links | `_data/navigation.yml` |
| Publication entries | One Markdown file per paper in `_publications/` |
| Photos and figures | `images/` |
| CV and paper PDFs | `files/` |

### Profile

In `_config.yml`, set the top-level `title`, `name` and `description`.
Under `author`, fill in `name`, `bio`, `employer`, `location`, `email`
and any relevant academic profiles. Blank optional fields stay hidden.
Upload a photo to `images/` and set `author.avatar` to its filename, such as
`portrait.jpg`. The GitHub account is already set to Burger-hub.

Keep these hosting settings:
```yaml
url: https://burger-hub.github.io
baseurl: ""
repository: Burger-hub/burger-hub.github.io
```

### Add a publication

Create a file such as `_publications/YYYY-MM-DD-short-title.md`.
Replace the placeholders below with the paper's real information:

```markdown
---
title: "Paper title"
collection: publications
category: manuscripts
permalink: /publications/short-title/
date: YYYY-MM-DD
venue: "Journal or conference name"
paperurl: "https://doi.org/REPLACE"
citation: "Authors. Paper title. Venue, year."
---

A short description of the paper.
```

Use `category: conferences` for conference papers.
The Publications page lists entries automatically.

### Add a CV later

Upload a PDF to `files/cv.pdf`, then add this under `main` in
`_data/navigation.yml`:
```yaml
  - title: "CV"
    url: /files/cv.pdf
```

## Deployment

In **Settings → Pages → Build and deployment → Source**, select
**GitHub Actions**. The existing `.github/workflows/jekyll.yml` builds with
the Jekyll version from the Gemfile and publishes updates pushed to master.
No extra workflow needs to be created. Check the **Actions** tab for the
latest deployment result.

The older **Deploy from a branch** build uses a Sass compiler incompatible
with the current template; use the bundled Actions workflow.

## Template examples

Original demo publications, posts, talks, teaching, portfolio entries and
unused pages are preserved in `_template_examples/` and excluded from the
published site. You can consult or copy them when adding content.

## Credits

Built with [AcademicPages](https://github.com/academicpages/academicpages.github.io),
based on Minimal Mistakes. The original MIT license is retained.

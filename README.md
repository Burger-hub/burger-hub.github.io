# Academic homepage

Source for https://burger-hub.github.io/, based on AcademicPages (Jekyll).

## Fill in your information

You can edit these files directly on GitHub: open the file, click the pencil,
make changes, then choose **Commit changes** on the master branch.

| Information | File |
| --- | --- |
| Name, title, affiliation, email, photo and profile links | `_config.yml` |
| Biography, research interests, education and honors | `_pages/about.md` |
| Navigation links | `_data/navigation.yml` |
| Publication entries | `_data/publications.yml` (newest first) |
| Photos and figures | `images/` |
| CV and paper PDFs | `files/` |

### Profile

In `_config.yml`, set the top-level `title`, `name` and `description`.
Under `author`, fill in `name`, `bio`, `employer`, `location`, `email`
and any relevant academic profiles. Blank optional fields stay hidden.
Upload a photo to `images/` and set `author.avatar` to its filename, such as
`portrait.jpg`. Google Scholar, ORCID, PubMed, GitHub and Bluesky are currently
hidden. To keep an optional field hidden, leave its YAML value empty (null),
such as `github:`, rather than using a quoted empty string.

Keep these hosting settings:
```yaml
url: https://burger-hub.github.io
baseurl: ""
repository: Burger-hub/burger-hub.github.io
```

### Add a publication

Add a new entry at the top of `_data/publications.yml`. The Publications page
renders the list automatically, numbers papers from newest to oldest and
highlights Bo Yang in the author list. Replace these example values:

```yaml
- title: "Paper title"
  authors:
    - "Bo Yang"
    - "Other Author"
  venue: "Journal or conference name"
  display_date: "Jul. 2026"
  type: "Journal article"
  doi: "10.xxxx/REPLACE"
```

Use the publication date precision you want readers to see in `display_date`.
If desired, add `description` for a short summary, or `image` and `image_alt`
for a figure you can share (for example `image: /images/paper-figure.png`).
The homepage name in the header links back to About Me; only Publications
appears as a separate navigation tab.

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

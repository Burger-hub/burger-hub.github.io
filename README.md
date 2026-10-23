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
| Publication entries and selection | `_data/publications.yml` |
| Photos and figures | `images/` |
| CV and paper PDFs | `files/` |

### Profile

In `_config.yml`, set the top-level `title`, `name` and `description`.
Under `author`, fill in `name`, `bio`, `employer`, `location`, `email`
and any relevant academic profiles. Blank optional fields stay hidden.
Upload a photo to `images/` and set `author.avatar` to its filename, such as
`portrait.jpg`. The current portrait is `images/bo-yang.jpg`.
Google Scholar is displayed as a disabled placeholder while its URL is blank.
Set `author.googlescholar` to your profile URL to enable the link, or set
`author.googlescholar_show: false` to hide the placeholder.
ORCID, PubMed, GitHub and Bluesky are currently hidden.
ResearchGate is linked from the sidebar. The affiliation is displayed as
`Ph.D. candidate at Tsinghua University` below the name; the separate employer
row is hidden.
To keep an optional field hidden, leave its YAML value empty (null),
such as `github:`, rather than using a quoted empty string.

Keep these hosting settings:
```yaml
url: https://burger-hub.github.io
baseurl: ""
repository: Burger-hub/burger-hub.github.io
```

### Add a publication

Add a record in `_data/publications.yml`. Set `selected: true` to show a detailed
representative work. Every `Journal article` also appears in All Publications,
grouped by `year` and sorted by `sort_key` in descending order. Both views use
the same record and highlight Bo Yang. Replace these example values:

```yaml
- title: "Paper title"
  authors:
    - "Bo Yang"
    - "Other Author"
  venue: "Journal or conference name"
  display_date: "Jul. 2026"
  type: "Journal article"
  selected: true
  year: 2026
  sort_key: 202601
  venue_abbr: "Journal abbreviation"
  volume: "1"
  issue: "2"
  article_number: "123456"
  doi: "10.xxxx/REPLACE"
  equal_contributors: ["Bo Yang", "Other Author"]
  corresponding_authors: ["Other Author"]
  pdf: "/files/publications/paper.pdf"
  image: "/images/publications/paper-overview.webp"
  image_alt: "Description of the paper's system overview"
  image_width: 1900
  image_height: 2368
  description: "A short introduction to the paper."
```

Use the publication date precision you want readers to see in `display_date`.
Upload the corresponding PDF and overview image to the paths above.
Selected Publications shows the title with available Publication, PDF and Code
links, then authors, venue/status and summary, followed by the overview image.
All Publications uses compact citations with abbreviated given names, linked
titles, journal, volume, issue, article number and year. Omit unavailable fields.
For an unpublished manuscript use `type: "Manuscript"` and `status: "Under review"`;
it can be selected, but is excluded from All Publications.
DOI values are kept as data for the Publication links and are not printed.
Use exact author names in `equal_contributors` and `corresponding_authors`
to display the co-first-author `#` and corresponding-author `*`.
See `files/publications/README.md` for the archived article versions and
figure extraction details. `files/publications/metadata-sources.md` records the
complete bibliography's source checks and any unconfirmed author-role fields.
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

# Starter Guide — How to Fill In This Template

This template has been pre-anonymized. Every personal field is now a placeholder.
Below is a checklist of what to change, in the order it usually makes sense to do it.

---

## 1. Site identity — `_config.yml`

Open `_config.yml` and replace these top-level values:

| Field | Replace with |
|---|---|
| `url` | `https://your-username.github.io` → your GitHub Pages URL |
| `description` | One-line site description (used for SEO and social previews) |
| `repository` | Your repo URL |
| `name` | Your full name (shown in the header and footer) |
| `title` | Your tagline (e.g., "PhD Student in X" or "Software Engineer at Y") |
| `email` | Your email address |

Then scroll down to the **social links** block and uncomment the platforms you
actually use, filling in your handles. Anything left commented out simply won't
appear on the site.

The **About section** (`about_content:`) is a multi-line HTML block — replace
the placeholder paragraphs with your own About / Research Interests / News /
Awards content. The structure is already there; you just swap text.

---

## 2. Profile photo — `images/profile.jpg`

The placeholder image at `images/profile.jpg` is a plain grey box reading "Your
Photo." Replace it with your actual photo (square aspect ratio works best).
Keep the same filename, or update the references in `_config.yml`
(`image`, `logo`, `favicon`, `about_profile_image`, and the `defaults` block).

---

## 3. Data files — `_data/*.yml`

Each YAML file controls a section of the site. Open them one by one and replace
the example entries with your own. The format is documented at the top of every
file.

| File | What it controls |
|---|---|
| `_data/education.yml` | Education section |
| `_data/experience.yml` | Experience / work history |
| `_data/projects.yml` | Project list on the **homepage** |
| `_data/projects-page.yml` | Project list on the standalone `/projects-page.html` |
| `_data/publication.yml` | Publications section (with CSL-JSON citation metadata) |
| `_data/blog_posts.yml` | External blog posts (Medium, personal blog, etc.) |
| `_data/skills.yml` | Skills, languages, and interests (already empty — uncomment template at top) |
| `_data/menu_items/menu.yml` | Navbar items |
| `_data/site_short_description_text.yml` | Short site descriptor used in some headers |

Tip: each entry is a list item under `- layout: ...`. Copy an existing block,
paste below, and edit. Keep indentation consistent (YAML is whitespace-sensitive).

---

## 4. Project posts — `_posts/`

These are the long-form project pages linked from the project cards. The
template ships with three examples to show different lengths:

- `2024-01-01-project-one.md` — short (foreword, features, tech stack, install)
- `2024-06-01-project-two.md` — medium (with a code example)
- `2024-12-01-project-three.md` — long technical writeup (math, citations, results)

Filename convention: `YYYY-MM-DD-slug.md`. Delete the examples once you have your
own posts. If you keep the slugs, also update the `redirect_from` lines or remove
them.

---

## 5. Blog posts — `_blog_posts/`

Long-form essays / tutorials hosted on this site. Two examples are included:

- `2024-01-15-your-first-blog-post.md` — basic post with Markdown, code, math
- `2024-06-01-a-longer-technical-post.md` — featured post with citations and references

Same filename convention as `_posts/`. Posts published here appear at
`/blog/<slug>/`.

For posts hosted *elsewhere* (Medium, Substack, your company blog) that you
just want to link to from this site, use `_data/blog_posts.yml` instead.

---

## 6. SEO

Update `robots.txt` so the sitemap line points at your domain.

`_config.yml` → `description`, plus per-post `description:` fields, drive the
meta tags via `jekyll-seo-tag`.

---

## 7. Run it locally

With Docker:

```bash
docker-compose up
```

With Ruby/Jekyll:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open `http://localhost:4000`.

---

## Quick "find every placeholder" sweep

If you want to double-check you haven't missed anything, this command lists
every line containing a placeholder string:

```bash
grep -rn -E "Your Name|your-username|your\.email@example\.com|Your Title|YYYY" \
  _config.yml _data/ _posts/ _blog_posts/ _drafts/ robots.txt
```

When that command returns nothing, you're done.

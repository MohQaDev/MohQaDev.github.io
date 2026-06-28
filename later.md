# Portfolio — how to edit / what to drop where

A cheat sheet for future-me. Everything is plain markdown + one `hugo.toml`. PaperMod theme, no custom layouts.

---

## 1. Run / build

```bash
hugo server     # live preview at http://localhost:1313 (auto-reloads on save)
hugo            # build into ./public/
```

After a fresh clone, init the theme submodule once:

```bash
git submodule update --init --recursive
```

---

## 2. Name-locked files (referenced from `hugo.toml` or content)

| File                                 | Path                                  | Referenced from                                                              |
| ------------------------------------ | ------------------------------------- | ---------------------------------------------------------------------------- |
| `MohammadAlQadi_CV.pdf`              | `static/`                             | `hugo.toml` socialIcons + `content/cv.md` + `content/about.md` + home blurb  |
| `AWS_CloudPractitioner_Certificate.pdf` | `static/`                          | `content/cv.md` + `content/about.md`                                         |
| `avatar.jpeg`                        | `static/img/`                         | `hugo.toml` → `homeInfoParams.Content` `<img src>`                           |
| `fullLogo.png`                       | `static/images/projects/joblood/`     | `content/projects/joblood/_index.md` → `cover.image`                         |
| `ISSLogo.png`                        | `static/images/projects/iss/`         | `content/projects/iss/_index.md` → `cover.image`                             |

If any of these are missing the site still builds — the link 404s or the image breaks. No cascading errors.

Rename → search/replace the reference, otherwise it'll break.

---

## 3. Project screenshots & demo videos

Filenames here are **not** locked — they live inside the markdown, so you edit one line to change them. Descriptive names (`donorHomePage.png`, `blood_storage.png`, etc.) are preferred over `1.png` / `2.png`.

| Markdown to edit                                       | Drop assets in this folder                              |
| ------------------------------------------------------ | ------------------------------------------------------- |
| `content/projects/joblood/_index.md` (auth + demo)     | `static/images/projects/joblood/home/` + `.../joblood/demo.mp4` |
| `content/projects/joblood/donor.md`                    | `static/images/projects/joblood/donor/`                 |
| `content/projects/joblood/lab-manager.md`              | `static/images/projects/joblood/lab-manager/`           |
| `content/projects/joblood/administrator.md`            | `static/images/projects/joblood/administrator/`         |
| `content/projects/iss/host.md` (video only)            | `static/images/projects/iss/host/demo.mp4`              |
| `content/projects/iss/client.md` (video only)          | `static/images/projects/iss/client/demo.mp4`            |

**To add more screenshots:** copy an `![alt](...)` line in the markdown and point it at a real file.
**To use fewer:** delete the extra lines.
**Videos use the raw `<video>` tag** (HTML inside markdown works because `unsafe = true` is set in `hugo.toml`).

---

## 4. Site sections

| What to change                                                    | Where                                                                                          |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Home intro text + featured-project blurbs                         | `hugo.toml` → `[params.homeInfoParams].Content`                                                |
| Home page avatar size / shape / border                            | `hugo.toml` → same `Content`, inline `style="..."` on the `<img>`                              |
| Page title in browser tab / SEO description                       | `hugo.toml` → `title`, `[params].description`                                                  |
| Top-nav menu items                                                | `hugo.toml` → `[[menu.main]]` blocks                                                           |
| Social icons (GitHub, email, CV button)                           | `hugo.toml` → `[[params.socialIcons]]` blocks                                                  |
| Default theme (dark / light)                                      | `hugo.toml` → `[params].defaultTheme`                                                          |
| About page (bio, education, skills, certs, contact)               | `content/about.md`                                                                             |
| Projects landing intro                                            | `content/projects/_index.md`                                                                   |
| **CV** page content (the `/cv/` route — what the top-nav links to) | `content/cv.md` (source-of-truth working copy lives at `assets/CV/Mohammad_AlQadi_CV.md`)      |
| JoBlood overview (description, tech-stack, auth screens, demo)    | `content/projects/joblood/_index.md`                                                           |
| ISS overview (description, architecture, 8-panel list)            | `content/projects/iss/_index.md`                                                               |
| Individual role / mode pages                                      | `content/projects/joblood/<role>.md` and `content/projects/iss/<mode>.md`                      |

---

## 5. Adding a brand-new project

1. Create a new section: `content/projects/<projectname>/_index.md` with frontmatter (title, summary, date, weight, cover, tags) and an overview body. Copy `joblood/_index.md` as a template.
2. Add role / detail markdown files inside that same folder.
3. Make matching asset folders under `static/images/projects/<projectname>/...`.
4. Add a featured-card blurb to `hugo.toml` → `[params.homeInfoParams].Content` if you want it linked from the home page.

The card on `/projects/` is generated automatically from the section's `_index.md` — no manual registration.

---

## 6. Things deliberately left simple

- **No custom layouts.** Everything renders through stock PaperMod templates. Don't drop files into `layouts/` unless you want to start overriding the theme.
- **`mainSections = []`** in `hugo.toml` stops the home page from auto-listing every page. Leave as-is unless you want post-list behaviour back.
- **`unsafe = true`** in the goldmark config is what lets the `<video>` tag and the avatar `<img style="...">` render. Don't disable it.
- **`themes/PaperMod` is a git submodule** — clone fresh requires `git submodule update --init --recursive`.
- **Administrator role currently has no screenshots** — placeholder text lives in the markdown.

---

## 7. Updating the theme

```bash
git submodule update --remote --merge themes/PaperMod
```

If a future PaperMod version renames a param or breaks something, the build error will name the file — usually a one-line fix in `hugo.toml`.

---

## 8. The `assets/` folder

`assets/` is where original / unprocessed media lives (organized by project). It's **not used by Hugo at build time** — only files copied into `static/` are served. Treat `assets/` as a working library; `static/` is what the site actually ships.

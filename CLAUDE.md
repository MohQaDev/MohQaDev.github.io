# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal portfolio site (Mohammad Al Qadi) built with **Hugo** and the **PaperMod** theme. Pure content + config — no custom layouts, no JS build step. Deployed to GitHub Pages at `https://MohQaDev.github.io/`.

## Commands

```bash
hugo server          # live preview at http://localhost:1313 (auto-reload)
hugo                 # build to ./public/
hugo --gc            # build + garbage-collect unused cache entries
```

After a fresh `git clone`, you must initialize the theme submodule or the build will fail:

```bash
git submodule update --init --recursive
```

To update the theme:

```bash
git submodule update --remote --merge themes/PaperMod
```

## Architecture

- **`hugo.toml`** is the single source of truth for site config, menu, social icons, and the **entire home page body** (under `[params.homeInfoParams].Content` — featured projects are inline HTML/Markdown here, not auto-listed).
- **`mainSections = []`** in `hugo.toml` is intentional — it stops PaperMod from auto-listing every page on the home page. Don't change unless you want post-list behavior back.
- **`markup.goldmark.renderer.unsafe = true`** is required for raw `<video>` and styled `<img>` tags in markdown to render. Don't disable.
- **`themes/PaperMod`** is a git submodule (no vendored copy). Stock theme only — `layouts/` is empty on purpose.
- **Content structure**: `content/projects/<project>/_index.md` defines a project section; sibling `.md` files (e.g. `donor.md`, `host.md`) are role/mode subpages. Cards on `/projects/` are auto-generated from each section's `_index.md` frontmatter (`title`, `summary`, `cover`, `weight`).

## Where to edit things

| What to change | Where |
|---|---|
| Home intro + featured-project blurbs | `hugo.toml` → `[params.homeInfoParams].Content` |
| Nav menu items | `hugo.toml` → `[[menu.main]]` blocks |
| Social icons (GitHub, email, CV) | `hugo.toml` → `[[params.socialIcons]]` |
| About page | `content/about.md` |
| Projects landing intro | `content/projects/_index.md` |
| CV page (`/cv/` route) | `content/cv.md` (working source: `assets/CV/Mohammad_AlQadi_CV.md`) |
| JoBlood overview | `content/projects/joblood/_index.md` |
| ISS overview | `content/projects/iss/_index.md` |
| Role/mode detail pages | `content/projects/joblood/<role>.md`, `content/projects/iss/<mode>.md` |

## Name-locked files (referenced from config)

Renaming these requires updating references:

| File | Path | Referenced from |
|---|---|---|
| `MohammadAlQadi_CV.pdf` | `static/` | `hugo.toml` (socialIcons, menu, home content), `content/about.md`, `content/cv.md` |
| `AWS_CloudPractitioner_Certificate.pdf` | `static/` | `content/cv.md`, `content/about.md` |
| `avatar.jpeg` | `static/img/` | `hugo.toml` home content `<img src>` |
| `fullLogo.png` | `static/images/projects/joblood/` | `content/projects/joblood/_index.md` → `cover.image` |
| `ISSLogo.png` | `static/images/projects/iss/` | `content/projects/iss/_index.md` → `cover.image` |

Project screenshot/video filenames (`donorHomePage.png`, `demo.mp4`, etc.) are **not** locked — they live in markdown and can be renamed freely as long as the markdown ref matches.

## `assets/` vs `static/`

`assets/` holds original/unprocessed media organized by project — it is **not** read by Hugo at build time and nothing in it is served. Only files under `static/` are published. Treat `assets/` as a working library; copy finished files to `static/images/projects/<name>/` when ready.

## Adding a project

1. `content/projects/<name>/_index.md` with frontmatter (`title`, `summary`, `date`, `weight`, `cover`, `tags`) — copy `joblood/_index.md` as a template.
2. Sibling `.md` files for role/detail pages.
3. Assets under `static/images/projects/<name>/...`.
4. Optionally add a featured-card blurb in `hugo.toml` → `[params.homeInfoParams].Content` to link it from home.

## Notes

- `later.md` (in repo root) is the author's own editing cheat sheet — useful cross-reference if something here is unclear. `guide.md` / `full_guide.md` are unrelated long-form writeups about the ISS Dashboard project, not site docs.
- `.hugo_build.lock`, `public/`, and `resources/` are build artifacts; don't commit changes to them deliberately.

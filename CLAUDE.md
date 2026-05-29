# Working with this repository

## How the user wants to collaborate

- **Do NOT run commands yourself.** The user prefers to run all commands (git, docker, etc.) themselves. Instead of executing, tell the user exactly *what* command to run and *where* to run it (which shell, which directory).
- This applies to: starting/stopping the local server, git commit/push, Docker commands, and any other shell action.
- Reading files, searching the codebase, and editing files is fine — it's the *running* of commands the user wants to do manually.

## Project overview

This is an [academicpages](https://github.com/academicpages/academicpages.github.io) (Jekyll) personal academic website, deployed via GitHub Pages at https://fmpizzi.github.io.

## Running locally (commands for the user to run)

Docker is the chosen local-preview method. From the repo root in PowerShell:

```powershell
docker-compose up          # start; open http://localhost:4000
docker-compose restart     # needed after editing _config.yml (Jekyll doesn't watch it)
docker-compose down        # stop
```

Most edits (`_includes/`, `_pages/`, `_data/`, `_publications/`, `*.scss`) auto-rebuild on save — just refresh the browser. `_config.yml` changes require a restart.

## Where things live

- Site-wide settings, author info, publication categories: `_config.yml`
- Top navigation menu: `_data/navigation.yml`
- Coauthor name → website directory: `_data/coauthors.yml`
- Home/bio page: `_pages/about.md`
- Research page (renamed from Publications, permalink `/research/`): `_pages/publications.html`
- Books page: `_pages/books.html`
- Individual publications: `_publications/*.md` (one file per entry; `category:` controls section; `published: false` hides an entry)
- Shared rendering template for publication entries: `_includes/archive-single.html`
- Custom CSS overrides: bottom of `assets/css/main.scss`
- CV PDF served directly from nav: `files/cv-pizzi.pdf`

# InferX

Learning modules about LLM inference and serving engines, organized into 14 categories covering model computation, systems, and production serving.

**Site address after deployment:** [mbellary.github.io/InferX-docs](https://mbellary.github.io/InferX-docs/)

## Local preview

Use Python 3.12 or newer. The deployment workflow uses Python 3.12.

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m mkdocs serve
```

Open the local address printed by MkDocs, normally `http://127.0.0.1:8000/`.

To build and validate all pages and internal links:

```sh
python -m mkdocs build --strict
```

Generated files go into `site/` and are excluded from Git.

## Add a chapter

Modules 1 and 2 have 41 chapter outlines (20 and 21 respectively). Their reading orders are in `docs/module-1.md` and `docs/module-2.md`; the authoring requirements are in `docs/learning-approach.md`. Establish the remaining module outlines first, then develop full chapters one at a time. Each chapter follows Concepts, Experiments, and Verification, with no code implementation.

1. Choose one of the existing category directories under `docs/`.
2. Copy `templates/chapter.md` into that directory with a descriptive filename.
3. Write the chapter through the lens of LLM inference and serving engines. Mark drafts clearly and cite primary sources for technical claims.
4. Add the chapter beneath its category in the `nav` section of `mkdocs.yml`, after the overview. Preserve the 14 top-level category names and their order.
5. Link the chapter from the category overview and replace its placeholder chapter text.
6. Use relative Markdown links, then run the strict build before submitting changes.

The chapter template lives outside `docs/` so unfinished template text is not published.

## GitHub Pages

The workflow in `.github/workflows/docs.yml` validates pull requests and builds and deploys pushes to `main`. It can also be started manually from the Actions tab on `main`.

To enable publishing for the repository:

1. Push these files to the repository's `main` branch.
2. In **Settings → Pages → Build and deployment**, set **Source** to **GitHub Actions**.
3. Open **Actions → Documentation** and run the workflow on `main` if the initial run did not deploy.
4. Check the deployment URL shown in the workflow and the `github-pages` environment.

The workflow uses GitHub's Pages artifact deployment, so a `gh-pages` branch is unnecessary. Pull requests only build and validate; publishing is restricted to `main`.

References: [MkDocs configuration](https://www.mkdocs.org/user-guide/configuration/) and [GitHub Pages custom workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).

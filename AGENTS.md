# Instructions for AI agents

This repository is the AMLab website (Jekyll, based on al-folio). Pushes to `master` are
deployed to GitHub Pages immediately by `.github/workflows/build_and_deploy.yml`, and
there is no PR review. **You are the only check before a change goes live.**

## Required before every commit/push

1. Run the build and confirm it exits with status 0:

   ```
   bundle exec jekyll build
   ```

   (If dependencies are missing: `bundler config set --local path 'vendor/bundle' && bundler install`.
   See `INSTALL.md`.)
2. If the build fails, fix the cause. Do **not** push a failing build, and do not
   bypass the check (no `--no-verify`, no disabling plugins or the workflow to make it pass).
3. Do not commit build output (`_site/`, `.jekyll-cache/`, `vendor/`).

## Rules

- Only change what the user asked for. Keep edits minimal.
- Never force-push to `master` or rewrite its history.
- Do not edit `.github/`, `CODEOWNERS`, `_config.yml`, `Gemfile`, `_layouts/`, `_includes/`
  or `_plugins/` unless the user explicitly asks; these affect the whole site. If asked,
  open a PR instead of pushing directly so an admin can review.
- Do not commit secrets, large binaries or unoptimised images (resize before adding to `assets/`).
- Pull/rebase before pushing (`git pull --rebase origin master`) and re-run the build
  if anything changed upstream.
- Use a short, descriptive commit message.

## Where content lives

- People: `_people/` · News: `_news/` · Projects: `_projects/` · Blog: `_posts/`
- Publications: `_bibliography/`
- Static assets: `assets/`

After pushing, check the Actions tab to confirm the deploy succeeded.

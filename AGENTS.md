# Instructions for AI agents

This repository is the AMLab website (Jekyll, based on al-folio). Changes go in through
pull requests that GitHub merges automatically once the `build` check passes. No human
approval is needed, so **you are responsible for the change being correct**. Merges to
`master` are deployed to GitHub Pages immediately by `.github/workflows/build_and_deploy.yml`.

## Workflow

Never push to `master` directly. Use a branch and an auto-merging PR:

```
git checkout -b <short-branch-name>
# make the change
bundle exec jekyll build        # must exit 0, see below
git add <files> && git commit -m "<short, descriptive message>"
git push -u origin <short-branch-name>
gh pr create --fill
gh pr merge --auto --squash
```

`gh pr merge --auto` queues the merge. GitHub merges as soon as `build` passes and leaves
the PR open if it fails. If it fails, read the log (`gh pr checks`), fix it on the same
branch and push again.

## Before pushing

1. Run `bundle exec jekyll build` and confirm it exits with status 0. (If dependencies
   are missing: `bundler config set --local path 'vendor/bundle' && bundler install`.
   See `INSTALL.md`.)
2. If the build fails, fix the cause. Do not bypass the check (no disabling plugins or
   workflows to make it pass).
3. The build only proves the site compiles, not that it looks right. For new photos, links
   or bibliography entries, check that they render (`bundle exec jekyll serve`).
4. Do not commit build output (`_site/`, `.jekyll-cache/`, `vendor/`).

## Rules

- Only change what the user asked for. Keep edits minimal.
- Never force-push, and never use admin overrides to merge a PR whose build failed.
- Do not edit `.github/`, `CODEOWNERS`, `_config.yml`, `Gemfile`, `_layouts/`, `_includes/`
  or `_plugins/` unless the user explicitly asks; these affect the whole site. If asked,
  say so in the PR description so a human can look at it before merging (omit `--auto`).
- Do not commit secrets, large binaries or unoptimised images (resize before adding to `assets/`).
- Rebase on `master` if the PR conflicts.

## Where content lives

- People: `_people/` · News: `_news/` · Projects: `_projects/` · Blog: `_posts/`
- Publications: `_bibliography/`
- Static assets: `assets/`

# GitHub

## `javascript` (bookmarklet) and `data` protocols in MarkDown links

The GitHub MarkDown renderer doesn't support either of the two protocols,
so no interactive links in your MarkDown files.

## `a[target="_blank"]` attribute support in MarkDown

The `target` attribute is not supported in links made using the `a` tag.

## `.gitmodules` through the web UI

GitHub won't check the submodule out upon just creation of `.gitmodules`.
A Git client needs to be used to checkout the submodule and push to the remote
so that the submodule files at the given hash appear as a submodule directory
in the GitHub web UI.

## Submodules on GitHub Pages

When a repository contains a submodule, that submodule appears as a subdirectory
in a GitHub Pages website.

Of course to update its contents the submodule needs to be updated through a Git
client as GitHub web UI doesn't have a control for updating submodules.

This is also useless for Service Workers because the scope is given by the
submodule directory and cannot intercept requests of the web app at the root
directory path.

## Sync with GitLab

GitLab Enterprise has a paid built-in feature for 2-way synchonization:
[Repository mirroring](https://docs.gitlab.com/ee/workflow/repository_mirroring.html)

[Tomas Wood made a tool](https://gitlab.doc.ic.ac.uk/tw1509/github-gitlab-sync)
which uses APIs and hooks to cross-synchonize repositories.

[Steve Perkins documented two approaches](https://steveperkins.com/migrating-projects-from-github-to-gitlab/):

- Named remotes
- Overloaded `origin`

Of course neither will synchronize non-Git objects, such as PRs and issues.

## SVGs in the README

GitHub will render SVG files in the readme and even play CSS animations in them.

## API Gotchas

- There is `stargazers_count` and `watchers_count` on the repository model and
  both are the same thing! The actual watchers are in `subscribers_count`
- An individual repo's details will contain its watcher count, but the get-repos
  endpoint will not return the `subscribers_count` field
- The `open_issues_count` field on the repository model combines the number of
  open issues and the number of open pull requests and there is no way to tell
  the two apart just based on that model
- The Activity API (events) does not have the right `payload.action` values or
  even correct payload fields as documented:
  https://github.com/TomasHubelbauer/tomashubelbauer/blob/main/index.js

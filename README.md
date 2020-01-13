# GitHub Knowledge Base

[**WEB**](https://tomashubelbauer.github.io/github)

## `javascript` (bookmarklet) and `data` links

The GitHub MarkDown renderer doesn't support either of the two protocols,
so no interactive links in your MarkDown files.

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

GitLab Enterprise has a built-in feature for 2-way synchonization, but it is paid.
[Repository mirroring](https://docs.gitlab.com/ee/workflow/repository_mirroring.html)

[Tomas Wood](https://gitlab.doc.ic.ac.uk/tw1509/github-gitlab-sync)
made a tool which uses APIs and hooks to cross-synchonize repositories.
This is an approach I will take as well. I will attempt to support non-Git objects as well.

[Steve Perkins](https://steveperkins.com/migrating-projects-from-github-to-gitlab/)
documented two approaches:

- Named remotes - this is fine, just need to remember to push both, but no non-Git objects
- Overloaded `origin` - this should be fine as well, but again, no non-Git objects

## SVGs in the README

GitHub will render SVG files in the readme and even execute CSS animations in them.

## To-Do

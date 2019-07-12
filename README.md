# GitHub Knowledge Base

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

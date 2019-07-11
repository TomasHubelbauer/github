# GitHub Knowledge Base

## `javascript` (bookmarklet) and `data` links

The GitHub MarkDown renderer doesn't support either of the two protocols,
so no interactive links in your MarkDown files.

### `.gitmodules` through the web UI

GitHub won't check the submodule out upon just creation of `.gitmodules`.
A Git client needs to be used to checkout the submodule and push to the remote
so that the submodule files at the given hash appear as a submodule directory
in the GitHub web UI.

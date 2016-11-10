# hook_example

A template with git hooks ensuring a script is run every commit, and changes made by that file are included in the commit.

Run `./hooks/mk_links.sh` once to symlink the hooks into the `./.git/hooks/ directory` and make them executable.

The pre-commit hook should work fine: edit the post-commit hook with the name of the script to be run at each commit, and the name of the file modified by the script.

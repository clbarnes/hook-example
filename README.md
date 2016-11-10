# hook_example

A template with git hooks ensuring a script is run every commit, and changes made by that file are included in the commit.

Run `./hooks/mk_links.sh` once to symlink the hooks into the `./.git/hooks/ directory` and make them executable.

The pre-commit hook should work fine: edit the post-commit hook with the name of the script to be run at each commit, and the name of the file modified by the script.

The logic is:

- As a pre-commit, create a file `.commit` showing that a commit is in progress.
- The initial commit happens.
- The post-commit checks for the existence of `.commit`
  - If not found, the process terminates and the commit is successful
- If `.commit` is found, `$SCRIPT` is executed, changing file `$CHANGED`.
- The commit is amended with any modifications to `$CHANGED`
- `.commit` is deleted

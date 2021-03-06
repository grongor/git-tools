grongor/console-tools
=====================

This package contains some usefull scripts which I use to simplify my daily tasks. If you like them then feel free to
use them. Any suggestions for improvements and new scripts are welcome - please send a pull request :-)

For some more complicated aliases you need the git completion script for the completion to work. If you don't have
the `__git_complete` function available in your bash then you can download it using this command:

`curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion`

Then add it into your `~/.bashrc` file using this line: `test -f ~/.git-completion && . $_`

pull-rebase-push - prp
----------------------

**Recommended alias:** `git config --global alias.prp "! '/path/to/git-pull-rebase-push.sh' "`

For usage information use `git prp -h`

This script will basically perform a **pull** on the master branch (only fast-forward, no merge commits will be
created), **rebases** the current branch with the master branch, performs a **merge** of the master branch with
the rebased branch and finally (optionally) **pushes** the changes.

checkout - c
----------------------

**Recommended alias:** `git config --global alias.c "! : git checkout ; '/path/to/git-checkout.sh' "`

Use as you would use the `git checkout` command

This script is simple wrapper for `git checkout`. It allows you to pass a number of Jira task instead of the full
branch name. If the task isn't found in your local branches or if you pass regular branch name (or whatever else)
then you get the default git error message.

branch-remove - brm
----------------------

**Recommended alias:** `git config --global alias.brm "! '/path/to/git-branch-remove.sh' "`

To clean all the merged branches use `git brm`

If you are tired of manually removing all the old branches then this script is for you. Just run `git brm`
and all your local branches that are already merged into master (therefore they are useless to keep)
will be removed. Simple as that.

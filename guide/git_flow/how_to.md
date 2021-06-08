## How to

### GitHub

#### Log in using ssh

GitHub offers three options for downloading the contents of a remote repository. We 
recommend using the _ssh key_ option to clone external repositories, especially when logging into 
GitHub using two-factor authentication. Follow these steps to 
{ref}`create a new ssh key <new_ssh_key>` and 
{ref}`add it to your GitHub account<adding_ssh_key>`.

#### Log in with a password when two-factor authentication (2FA) is enabled

One can generate {ref}`access tokens<generating_gh_tokens>` and use them instead of your password 
to log in to GitHub. Nevertheless, depending on your account security settings, access tokens may 
produce errors, preventing downloading from remote repositories. 

#### Reference pull requests and issues in your comments

* Use {ref}`Cross Links <referencing_issue_and_pr>` to  connect different conversations 
  within a repository. When commenting, type `#` to bring up a list of suggested 
  __issues__ and __pull reqests__, and select the issue or pull request 
  number to reference it. These references are automatically converted to shortened links to the issue or pull request. 
* If you are opening a pull request that fixes the question proposed in an issue, 
  add `closes #[issue/PR number]` in the pull request message. This will 
  close automatically the issue when the reviewer approves and merges the pull request.
  
### Git

#### _Git push_ and _Git pull_. Remote branches  

Once you are done introducing your new additions to the project, and your files are ready to be 
uploaded, the easiest way to create a new remote branch to host your local work is using 
`git push [remote alias] [local branch name]`. This will create a remote branch (named after the 
source branch) that will store the modifications commited on your _local branch_. If one is 
interested in having a remote branch labelled differently, Git allows you to choose the 
name of the remote branch by adding to `push` the tag 
`[source local branch]:[destination remote branch]`. In this 
way, the sentence `git push origin local feature:remote feature` will push to the remote 
repository (referred by _origin_) the changes introduced in your local branch _local feature_ to 
the remote branch _remote feature_.
In case that you are suffering some problems when pushing your commits, you can always override 
the remote branch with the contents pushed from local by using the command 
`git push -f`. Since the remote branch is, by default, the "true" Git history, what 
this command does is telling Git that the true source is instead the local branch, giving it 
preference over the remote one. One must be extremely careful when using this option, as it will 
erase the contents of the remote branch.

You can download a remote repository using `git pull`. Sitting on the target branch where you want 
to save the remote content, you can write `git pull [remote alias] [remote branch name]` to 
download the last version of the source branch. 

:::{admonition} Resources
:class: seealso
A complete description of `git pull`/`git push` and the options they offer can be found in the following links:
* {ref}`Syncing tutorial<sync_remote>` and references therein. 
* {ref}`Git push<push>` documentation page.
* {ref}`Git pull<pull>` documentation page. 
:::

#### Moving across commits

`git checkout [commit reference]` moves the current tip to a previous committed change, the latter 
being specified by a __hash__ number. Nevertheless, this method is rather tedious and 
inconvenient, the use of _relative references_ being a more appropriate option. Starting from a 
specific branch or commit, one can move to previous snapshots by using either `^` (this 
command moves the tip upwards one commit at a time) or `~<number>` (this commands moves the tip 
upwards as many times as the given value). Considering the scenario where the last commit 
is referred by `HEAD`, one can write `git checkout HEAD~3` in order to relocate the tip three 
commits back. 

:::{admonition} Hash
:class: tip
All committed changes are identified by a unique hash number (`git log` displays a complete list 
containing all commits and their references). Git usually requires only a few characters of the 
hash to 
identify the corresponding commit.


#### Interactive rebase
`Git rebase --interactive` is broadly used to review commit changes and apply further 
modifications to old commits. The unflagged command, `git rebase`, is used to compress the changes 
made on the source branch, and apply them on top of the target branch, achieving in this way a 
flat Git history. `git rebase` also avoids merging conflicts when pushing new 
content to remote repositories, as it allows the coder to rebase his/her local changes on top of 
the most recent version stored in remote. 

The interactive mode (called via `git rebase -i`) gives the user the opportunity to rebase 
individual commits interactively. More interestingly, it allows rebasing changes committed on the 
current branch. This opens the door to revisit old commits and correct small errors, such as 
erroneous commit messages. One can amend or squash multiple commits, delete non-desired changes, 
reset `HEAD` to a specific label, relabel the current `HEAD` with a new name, etc. In order to 
modify old commits, one should write `git rebase -i HEAD~#` where "#" is the number of previous 
commits to be rebased. For further reading, we refer {ref}`this tutorial<interactive_rebase>` 
about rebasing Git history with the interactive mode.

#### Rewrite Git history

Before pushing local changes to remote, a recommended practice is rewriting Git history. This 
facilitates the reviewing process, while helping you to understand and clarify the working flow. 
We have already mentioned one tool for rewriting Git history (`git rebase -i`), but Git offers 
other utilities for customizing the historical commit changes. Read this 
{ref}`this reference<rewriting_git_history>` to understand the tools available to achieve your 
desired Git history. 

#### Defer changes 

You have probably needed to switch branches while working on some feature of a 
project. Git does not allow you to checkout to another branch without committing the modified 
files. One can use `git stash` to temporarily shelve these changes, so you can freely move through 
the Git history, work on new features and, once you are done, come back and _unstash_ the 
modifications. This command becomes extremely useful when your code is not ready to be committed, 
but you need to switch to a different working environment. As mentioned, `git stash` saves your 
uncommitted changes for later use, allowing you to create new commits, modify new files or switch 
branches. In order to re-apply the archived changes, you should use `git stash pop` (or 
`git stash apply` if you are interested in maintaining them in your stash). Keep in mind that Git 
will not stash untracked or ignored files. For more information about this topic, we recommend 
reading {ref}`this page<git-stash>`. 

#### Inspecting the state of the repository

To retrieve information about untracked files, 
the staging area and the working directory, one should use the `git status` command, which 
displays all modified files on your working directory. On the other hand, `git log` command shows 
the Git history of your project, listing all committed changes made on your current branch. This 
{ref}`page<log>` explains the multiple options and tools that `git log` can offer. 



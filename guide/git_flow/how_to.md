## How to

### GitHub

#### Log in using ssh

You have to {ref}`create an ssh key <new_ssh_key>` and {ref}`add it to your account <adding_ssh_key>`.

#### Log in with a password when 2-factor authentication (2FA) is enabled

Generate access tokens following {ref}`this tutorial <generating_gh_tokens>`, 
and use the tokens instead of your password.

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

Once you are done introducing your additions to the project and your files are ready to be uploaded, the easiest way to create a new remote branch to host your local work is using `git push [remote alias] [local branch name]`. This will create a remote branch (named after the source branch) that will store the last modifications of your _local branch_. Git allows you to choose the name of the remote branch, adding to `push` the tag `[source local branch]:[destination remote branch]` instead of `[local branch name]`. In this way, the sentence `git push origin _local feature_:_remote feature_` will push to the remote repository (referred by _origin_) the changes introduced in your local branch _local feature_ to the remote branch _remote feature_.
In case that you are suffering some problems when pushing your commits, you can override the remote branch with the contents pushed from your local branch using `git push -f` instead of `git push`. The remote branch being the "true" Git history by default, what this command does is telling Git that the true source is the local branch, having preference over the remote one. One must be extremely careful when using this option, as it will erase the remote branch content.

You can download a remote repository using `git pull`. Sitting on the branch where you want to store the remote content, you must introduce `git pull [remote alias] [remote branch name]` to download the last version of the introduced remote branch. 

:::{admonition} Resources
:class: seealso
A complete description of `git pull`/`git push` and the options they offer can be found in the following links:
* {ref}`Syncing tutorial<sync_remote>` and references therein. 
* {ref}`Git push<push>` documentation page.
* {ref}`Git pull<pull>` documentation page. 
:::

#### Interactive rebase
Follow {ref}`this tutorial<interactive_rebase>`

#### Rewrite git history
Follow {ref}`this tutorial<rewriting_git_history>`

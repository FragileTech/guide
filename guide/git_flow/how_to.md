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

#### Interactive rebase
Follow {ref}`this tutorial<interactive_rebase>`

#### Rewrite git history
Follow {ref}`this tutorial<rewriting_git_history>`

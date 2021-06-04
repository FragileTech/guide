## Bibliography

### Git
#### Introduction to Git
Slides and articles recommended for a gentle introduction to Git.

```{eval-rst}
.. [git_vadim_presentation] 
   A set of slides that explain the main advantages of using version control and the basic concepts needed to understand git.
   It is an introductory tutorial illustrating the importance of using Git in a collaborative environment. 
   It incorporates a summary of the essential commands, and helpful links to Git bibliography and interactive courses.

    http://vmarkovtsev.github.io/mipt_web_2015/02_git/index.html

.. [git_handbook] 
   An article containing a nice introduction to Git. It describes the basic commands and its most used features.

   https://guides.github.com/introduction/git-handbook/
   
.. [learn_git_resources]
   A collection of resources to learn about Git.
   
   https://try.github.io/
```
#### Interactive labs to learn Git
Online courses and step-by-step demonstrations explaining the most popular Git commands and collaborative processes
```{eval-rst}
.. [git_lab_fundamentals] 
    Interactive lab to learn the fundamentals of git.

    https://gitimmersion.com/lab_01.html
    
.. [git_lab_branching] 
    Interactive lab to learn how git branching works.

    https://learngitbranching.js.org/

.. [course_using_git] 
    Free online Git course. After completing it you will understand Staging, cloning, branching, 
    and collaborating with Git.

    https://www.pluralsight.com/courses/code-school-git-real
```

#### Git Basics 
```{eval-rst}
.. [saving-changes]
   Introductory tutorial to the saving process in Git. 
   
   https://www.atlassian.com/git/tutorials/saving-changes 
   
.. [recording-changes]
   Page containing a complete description about the three-stage process in Git.
   
   https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository

.. [three-trees]
   Page containing an introduction to Git's internal state management system and reset command. 
   
   https://www.atlassian.com/git/tutorials/undoing-changes/git-reset
   
.. [branch]
   Explains the basics about branching in Git. 
   
   https://www.atlassian.com/git/tutorials/using-branches

.. [merge-basic]
   Gentle tutorial explaining the concepts and mechanisms behind `git merge`.
   
   https://www.atlassian.com/git/tutorials/using-branches/git-merge

.. [rebase-basic]
   Tutorial explaining the concepts and mechanisms behind `git rebase`.
   
   https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
   
.. [rebase-vs-merge]
   A clear overview over the two merging strategies.
   
   https://www.atlassian.com/git/tutorials/merging-vs-rebasing
```

#### Reference
```{eval-rst}
.. [git_cheat_sheet] 
    Cheat sheet containing the most common Git commands. Recommended as a quick 
    reference guide for solving common issues or remembering how to write a command.

    https://education.github.com/git-cheat-sheet-education.pdf

.. [pro_git_book] 
    Contains everything there is to know about Git. 
    It's pretty hardcore, so we recommend using it as a last resort.

    https://git-scm.com/book/en/v2
    
```
#### How To
```{eval-rst}
.. [interactive_rebase] 
    Interactive rebase with Gitkraken.

    https://support.gitkraken.com/working-with-repositories/interactive-rebase/

.. [rewriting_git_history] 
    Explains how to rewrite git history.

    https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History
    
.. [rewriting_git_history2]
    Tutorial listing the rewriting options Git offers.
    
    https://www.atlassian.com/git/tutorials/rewriting-history#git-rebase-i
    
.. [sync_remote]
    Explains how to work with remote repositories. Description of `git push` and `git pull` commands. 
    
    https://www.atlassian.com/git/tutorials/syncing

.. [push]
   `Git push` documentation page.
   
   https://git-scm.com/docs/git-push

.. [pull]
   `Git pull` documentation page. 
   
   https://git-scm.com/docs/git-pull
   
.. [git-stash]
   Explains how to stash uncommitted changes with `git stash`.
   
   https://www.atlassian.com/git/tutorials/saving-changes/git-stash
   
.. [log]
   Page listing the options offered by `git log`. 
   https://www.atlassian.com/git/tutorials/inspecting-a-repository
```

### GitHub
#### Pull Requests (PR)
```{eval-rst}
.. [about_pull_requests] 
   Explains the basics about Pull requests.

   https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests

.. [creating_a_pull_requests] 
   Tutorial about how to open a new pull request.

   https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request
   
.. [commenting_on_pull_requests] 
   Explains how to use the GitHub interface to comment on a pull request.

   https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request
   
.. [referencing_issue_and_pr]
   Explains how to reference issues from PRs and vice-versa.
   
   https://docs.github.com/en/github/writing-on-github/autolinked-references-and-urls#issues-and-pull-requests

.. [issues-tools]
   List of available features on Issues page. 
   
   https://guides.github.com/features/issues/

.. [write-issue]
   Good practices for writing a proper GitHub issue. 
   
   https://medium.com/nyc-planning-digital/writing-a-proper-github-issue-97427d62a20f
```

#### Code reviews
```{eval-rst}
.. [intro_code_reviews] 
   Introductory article to code reviews containing useful tips.

   https://www.evoketechnologies.com/blog/simple-effective-code-review-tips/

.. [code_review_checklist_1] 
   Blog post containing a check list for performing more efficient code reviews.

   https://www.evoketechnologies.com/blog/code-review-checklist-perform-effective-code-reviews/
   
.. [code_review_checklist_2] 
   Blog post containing a check list describing different principles of code reviews.

   https://dev.to/codemouse92/10-principles-of-a-good-code-review-2eg
   
.. [nicer_code_reviews] 
   Blog post containing tips for encouraging contributions and being nice during a code review.

   https://developers.redhat.com/blog/2019/07/08/10-tips-for-reviewing-code-you-dont-like/
```

#### Accessing GitHub
```{eval-rst}
.. [new_ssh_key] 
   Explains how to generate a new ssh key so you can log in to GitHub with it.

   https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

.. [adding_ssh_key] 
   Explains how to add a new ssh key to your GitHub account.

   https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account
   
.. [generating_gh_tokens] 
   Explains how to use authentication tokens to avoid 2FA errors.

   https://medium.com/@ginnyfahs/github-error-authentication-failed-from-command-line-3a545bfd0ca8
```

#### Reference
```{eval-rst}
.. [github_docs] 
   GitHub.com official documentation.

   https://docs.github.com/en/github
```



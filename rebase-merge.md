# Joining histories

Once you have finished your work, and the new modifications satisfy your criteria, you are in position to integrate all these changes into the main line of development and share your thoughts with your teammates. Git offers two basic utilities to incorporate code from one branch into another, `git merge` and `git rebase`. Despite sharing a common goal, the method and philosophy behind these two are very different.

:::{admonition} Remember
:class: important
Git branches are merely pointers to specific commits in Git history. They are not new repositories or folders. 
:::

## Git Merge

`git merge` combines content from different branches into a single, unified commit. The process is the following: `git merge` takes two branch pointers and identifies their common commit ancestor. Once git locates this point, it generates a unique "merge commit" (in the current branch) that combines all committed changes from their common parent. This new commit is unique in the sense that it depends on two parent commits. `git merge` only modifies the target branch; the source branch history remains unaltered. 

## Git Rebase

`git rebase` is the second method to integrate changes. Rebasing compresses the content of the source branch into a single patch and integrates it on top of the target branch. In this way, we transfer the finished work from one branch to another, rewriting and flattening the history. It appears as if the entire sequence of commits had been created from a different commit, achieving a linear project history. Internally, what Git is doing is replicating the commit sequence of the source branch onto the target base, creating new commits for each commit in the original branch. The primary motivation for using `git rebase` is to achieve a linear project history. 

:::{figure-md} rebase
:width: 400px
:align: center

![rebase](guide/git_flow/images/rebase.png)

`git rebase` captures the content from one branch and reapplies it on top of another. In that way, rebasing changes the base of our branch to a different commit
:::

:::{admonition} Good practices
:class: tip
An excellent exercise to avoid merging conflicts when pushing your content, either to the main branch or to a remote repository, is rebasing your changes with the most recent version of main. In this way, you guarantee that your changes are based on the most updated version of the repository, facilitating the merging process.
:::

Consider the following scenario: you have worked for several days on an additional feature for a program. Meanwhile, the main line has been updated multiple times in the remote repository by your teammates, leaving your files obsolete. If you want to push your work to remote and open a Pull Request to merge your fresh additions to "main", a good practice is rebasing your content with the most updated version of the remote repository.

1. First, you have to download the remote main branch to include all these new modifications that have been added: 
`git pull origin main`
2. Once you have your local main branch updated, you have to move to your local working environment: 
`git checkout feature`
3. Sitting on your branch, rebase your modifications with "main": 
`git rebase main`

_Eureka_! Now your branch is based on the remote main branch and it is ready to be pushed without any problem. 

## Git Rebase -i 
An interesting option `git rebase` offers is the interactive mode. The flag `-i` begins the interactive mode, which gives you the opportunity of rebasing the commits individually as well as modifying their properties during the process. In this way, you can determine how the sequence of commits is transferred to the new base. 
Besides, this mode opens the door to rewriting your Git history, using `git rebase -i HEAD~` plus the number of commits you want to rewrite. With this command, instead of rebasing against a distinct branch, you are "shifting" your base to the same point, while allowing you to remodel the structure of your commits. `git rebase -i` is extensively used (and widely recommended) before pushing your modifications to remote; you can rectify your changes, reorganize your history, and keep the number of commits to a minimum.

`git rebase` not only allows you to rewrite your history, but it reinforces the concept of branches as pointers: next to `git rebase` must be placed a reference, either the label that refers to an individual commit (to rewrite your history); or a target branch to integrate your changes linearly. 

:::{admonition} Resources
:class: seealso 
You will be able to find more literature about merging utilities in the following links: 
* {ref}`Tutorial<merge-basic>` about `git merge`. 
* In-depth {ref}`tutorial<rebase-basic>` about `git rebase`, including the interactive mode. 
* {ref}`Conceptual discussion<rebase-vs-merge>` about the two merging strategies.
* Immerse in the most complete {ref}`source<pro_git_book>` about Git. 
* We encourage to exercise `merge` and `rebase` tools by using the {ref}`interactive tutorials<git_lab_branching>`.  
:::

## Rewriting history
Before pushing your modifications to your shared repository, having a clean, organized history is strongly recommended to help the reviewing process to your comrades (and, of course, to facilitate your understanding of the working flow). Git offers multiple work flow customization tools that give you total control over the project development. We mentioned `git rebase -i`, but there are more options to restructure your Git commits, such as `git commit --amend`. These {ref}`two<rewriting_git_history>` essential {ref}`references<rewriting_git_history2>` contain __everything__ you should know about history-rewriting commands. These sources expose the topic in such a precise and straightforward manner that we are unable to include something relevant to the discussion.

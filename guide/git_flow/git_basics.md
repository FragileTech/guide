# Introduction to Git
Git is a powerful tool that permits parallel and asynchronous work while maximizing productivity and collaboration among team members. Despite the countless benefits Git offers, it requires time and dedication to learn and master. In this section, we will try to cover and define the most general Git concepts that may lead to misleading conclusions. Having an accurate understanding of these terms will facilitate immensely your learning path. This section summarizes the content of different reviews and guides presented throughout this page; we strongly encourage to practice the fundamental Git utilities using {ref}`this lab<git_lab_branching>`, which includes a beginner-oriented tour about the concepts you are working on. 

## The three stages of Git 


:::{figure-md} three_stages
:width: 300px
:align: center
![stages](images/three.png)
:::


Every file in a Git repository goes through three stages: __modified__, __staged__ and __committed__.
 * _Modified_ is the stage where you make some additions (or _modifications_) to the project. Changes are applied in the working directory (the Git tree in sync with your local machine), leaving unchanged the original code.
 * The second step is tracking modified files. The command `git add [files]` updates the Git index using the provided `files` and pushes them to the _staging_ area. Files included in this "space" are monitored by Git, notifying when new changes are applied. This area is the prior step to commit the fresh modifications to your code; it stores the changes that you want to include in the next snapshot.   
 * The last step consists in _committing_ your modifications. `git commit` records a snapshot of the changes kept in the staging area while creating a new timestamp in the history. Adding the option `-m` allows you to pass a commit message. Git maintains a history of all the commits that were made, generating a "timeline" with commits ordered in time. Sitting in a particular commit, all previous ones are called _ancestors_, usually designated with arrows in descriptive illustrations.

:::{admonition} Remember
:class: important
Files in a working directory can be in two states: __tracked__, files that were in the previous snapshot or were added to the staging area; or __untracked__, files that were not present in the last commit and are not staged. Git will not include untracked files in the next historical snapshot until you explicitly add them. Git notices new modifications introduced in tracked files. 
:::

:::{admonition} Resources
:class: seealso 
You will discover more information and material about these concepts in the following links:
* An introductory {ref}`tutorial <saving-changes>` to saving changes in Git.
* A (maybe too comprehensive) {ref}` complete description <recording-changes>` of the recording process in Git.
* Tutorial focused on the Git command `reset`, the first part contains an enlightening {ref}`description<three-trees>` of Git's internal state management system. 
:::

## Commit, branches and heads

As previously mentioned, `git commit` is a daily command used to save the relevant changes in our repository. Git preserves a history of which commits were made and when; new commits arise from older commits (called parents or ancestors), which are used as a basis to build new commitments. 

:::{figure-md} commit
:width: 300px
:align: left

![commit](images/commit.png)

New commit is based off its ancestors
:::

Most VCS's offer the possibility of creating safe "rooms" where you can play and test new inclusions to your model. Contrary to other VCS's, Git branches are simply __pointers__ to commits saved in Git history. Branches are not new isolated copies of your project (a new container for your commits), but they are references to specific commits. Developers usually represent Git branches as independent ramifications (or bifurcations) from the main development line. They are built using the `git branch` command or `git checkout -b`. 

When using `git branch new_feature`, you are creating a new pointer labeled `new_feature` that refers to the last commit (the repository remains __unchanged__). Although at first glance this operation could seem pointless, branches reach their full potential as we generate new commits. 

Moving to the new branch, new commits will be referred now by `new_feature`. We can return to our principal branch by using the command `git checkout main` (remember, branches are simply references; `main` is a tip pointing to _c2_). We will develop a ramification when committing a new change from `main`. Despite being conceived by the same commit _c2_, _c3_ and _c4_ are disconnected entities that "exist" in different branches. Sitting on _c3_ (that is, going back to `new_feature`), we can make several new commits that depend neither on _c4_ nor on `main`. As promised, we are able to write fresh code without affecting the main development line. 


:::{figure-md} branch1
:width: 310px
:align: left

![branch1](images/branch1.png)

Branches are __pointers__ to specific commits in Git history. Sitting on the new branch `new_feature`, the next commits will be referred by the latter
:::

:::{figure-md} branch2
:width: 310px
:align: right

![branch2](images/branch2.png)

Going back to the branch `main`, a new commits will generate a bifurcation in the history. Commits from different branches are disconnected
:::


      


Once we are satisfied with the changes made in our code, we can integrate the multiple commits created in our supporting branch into the main line by using `git merge`. This sentence generates a dedicated commit that combines the development of the two branches (current and target). Merge commits are unique as they are based on two parent commits. One should notice that merge commits are produced in the current branch; `git merge` updates the current branch with the modifications made in the target branch, leaving the latter unaffected. 

:::{figure-md} branch3
:width: 300px
:align: center

![branch3](images/branch3.png)

`git merge` generates a new commit that unifies the two history lines 
:::

Closely related to the fact that branches act as a pointer is the concept of `HEAD`. `HEAD` is the name used to refer to the commit we are working on. It normally points to the most recent commit (which is also referred to by the current branch). We change the position of `HEAD` by using `git checkout`; when you are applying this sentence to shift from one branch to another, what you are doing is migrating the tip `HEAD` between these branches. We can move `HEAD` to a specific commit (and detached it from a branch) by using `git checkout` and the label of the commit. In the same way, we are able to move the position of a branch by typing `git branch -f [branch_name] [position]`. 

:::{admonition} Resources
:class: seealso 
If you are interested in delving into the ideas explored in this section, explore the following links:
* You will find all the information you need about Git branches on this {ref}`page<branch>`.
* Enlightening {ref}`tutorial<merge-basic>` about merge command. It includes the multiple 
  options this command offers, and the different merge strategies. 
:::



## Joining histories

Once you have finished your work, and the new modifications satisfy your criteria, you are in position to integrate all these changes into the main line of development and share your thoughts with your teammates. Git offers two basic utilities to incorporate code from one branch into another, `git merge` and `git rebase`. Despite sharing a common goal, the method and philosophy behind these two are very different.

:::{admonition} Remember
:class: important
Git branches are merely pointers to specific commits in Git history. They are not new repositories or folders. 
:::

### Git Merge

`git merge` combines content from different branches into a single, unified commit. The process is the following: `git merge` takes two branch pointers and identifies their common commit ancestor. Once git locates this point, it generates a unique "merge commit" (in the current branch) that combines all committed changes from their common parent. This new commit is unique in the sense that it depends on two parent commits. `git merge` only modifies the target branch; the source branch history remains unaltered. 

### Git Rebase

`git rebase` is the second method to integrate changes. Rebasing compresses the content of the source branch into a single patch and integrates it on top of the target branch. In this way, we transfer the finished work from one branch to another, rewriting and flattening the history. It appears as if the entire sequence of commits had been created from a different commit, achieving a linear project history. Internally, what Git is doing is replicating the commit sequence of the source branch onto the target base, creating new commits for each commit in the original branch. The primary motivation for using `git rebase` is to achieve a linear project history. 

:::{figure-md} rebase
:width: 400px
:align: center

![rebase](images/rebase.png)

`git rebase` captures the content from one branch and reapplies it on top of another. In that way, rebasing changes the base of our branch to a different commit
:::

:::{admonition} Good practices
:class: tip
An excellent exercise to avoid merging conflicts when pushing your content, either to the main branch or to a remote repository, is rebasing your changes with the most recent version of main. In this way, you guarantee that your changes are based on the most updated version of the repository, facilitating the merging process.
:::

Consider the following scenario: you have worked for several days on an additional feature for a program. Meanwhile, the main line has been updated multiple times in the remote repository by your teammates, leaving your files obsolete. If you want to push your work to remote and open a Pull Request to merge your fresh additions to _main_, a good practice is rebasing your content with the most updated version of the remote repository.

1. First, you have to download the remote main branch to include all these new modifications that have been added: 
`git pull origin main`
2. Once you have your local main branch updated, you have to move to your local working environment: 
`git checkout feature`
3. Sitting on your branch, rebase your modifications with _main_: 
`git rebase main`

_Eureka_! Now your branch is based on the remote main branch and it is ready to be pushed without any problem. 

### Git Rebase -i 
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

### Rewriting history
Before pushing your modifications to your shared repository, having a clean, organized history is strongly recommended to help the reviewing process to your comrades (and, of course, to facilitate your understanding of the working flow). Git offers multiple work flow customization tools that give you total control over the project development. We mentioned `git rebase -i`, but there are more options to restructure your Git commits, such as `git commit --amend`. These {ref}`two<rewriting_git_history>` essential {ref}`references<rewriting_git_history2>` contain __everything__ you should know about history-rewriting commands. These sources expose the topic in such a precise and straightforward manner that we are unable to include something relevant to the discussion.






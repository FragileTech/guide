## FAQ

#### What is Git?
A fundamental key in collaborative projects is having control (or a tracking history) over the 
modifications made on the project. Git is a popular distributed version control system broadly 
used in software development.

Git facilitates the addition of novel content through the use of _branches_, 
bifurcations in the tracking history of the project that allows the creation 
(or update) of extra features in a secure, fully controlled sandbox. 

Each project has a default branch (usually named `master` or `main`) that act as the source of truth 
for the project's code. We develop new features in different branches, and we integrate them into the default branch
after a review process.

#### What is the difference between Git and GitHub?
<!---Naming conventions in programming languages is anything but clear. While HTML and CSS describe what the code is about, others like C++ are named after its origin. We have also the case of Java and JavaScript,  -->
As mentioned, Git is a popular _Version Control System_ used to manage a wide variety of projects. 
Git is installed and maintain in your local machine, and it keeps a record of your programming 
versions. What makes Git unique from the rest of its competitors is its branching model, which 
allows you to test and try new ideas without touching the mainline. 

Having said that, what is GitHub's role? _GitHub_ is a Git repository hosting service. It is a cloud-based database where people can track and share with other developers their local Git repositories. Unlike Git, GitHub presents a graphical user interface to administer your projects using its built-in control tools. 

Although they are already very interesting utilities on their own, <!---Being interesting 
utilities separately, -->the real collaborative environment boosts when Git and GitHub work 
together. You can share your projects through GitHub, giving your teammates the opportunity to 
review and comment on your additions. As the project evolves, new branches are created to introduce 
new changes, allowing the group to work on distinct features without overwriting each other's work 
during the process. This philosophy promotes coordination among comrades, making possible a 
collaborative development process.

#### What is a Pull Request?

After finishing writing the new feature of your collaborative project, you will be eager to merge 
your fresh content with the main branch. However, before adding the new features to the mainline, 
your code should pass a reviewing process for discussing with your colleagues the potential and 
suitability of your changes. Thus, before merging the pushed branch into the base one, you must 
open a __Pull Request__ to notify others about the additions you have been working on, compare 
the differences between your branch and the repository base branch, and debate about further
commits to improve your work.

After opening a Pull Request, you will see a discussion panel where your collaborators can 
review your changes, suggest new additions or recommendations, and even contribute to the Pull 
Request with new commits. You can also add new content by pushing new commits from your branch 
to the open Pull Request. 

#### What is an Issue?

__Issues__ are used to suggest new additions, tasks, enhancements, or questions related to the 
repository. Any collaborator can open a new issue (in the case of public repositories, any GitHub 
member can create a new issue), which opens a discussion thread where team members can address 
the topic. 

:::{admonition} Resources
:class: seealso
One can find more information about Pull Requests and Issues along these pages:
* How to collaborate with {ref}`Pull Requests<about_pull_requests>`. 
* Reference guide for {ref}`creating a Pull Request<creating_a_pull_requests>`.
* {ref}`Available features<issues-tools>` in Issues page. 
* How to write a {ref}`proper issue<write-issue>`. 
:::

#### What is a branch? 

When developing new features, coders work in safe spaces where their changes do not affect 
the project's mainline. Most VCS's offer a secure, virtual environment so that programmers can 
work freely without worrying about "corrupting" the project. Git goes one step further in 
providing these isolated environments by promoting the use of branches. Git branches are 
merely pointers, references to committed changes. As one develops new features and stores them, 
the branch represents the tip of that series of commits. In this way, Git branches are
notably lightweight, as they are not containers keeping incoming commits (remember, they are solely 
references to specific commits in Git history). 

Consider the scenario where you want to correct a bug. Immediately, you spawn a new branch from 
the project's mainline. This new branch creates a bifurcation, isolating all incoming 
additions while protecting the main base from unstable code. Once you are satisfied with your 
changes and how the Git history looks, you can safely merge your fresh features into the 
mainline. 

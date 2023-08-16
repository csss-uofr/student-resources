# Git Resources

A curated list of amazingly awesome Git tools, resources and shiny things.

## Contributing

Pull requests on interesting tools/projects/resources are welcome.

## Table of Contents

- [Git Commands](#git-commands)
  - [Installing Git](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/set-up-git)
  - [Getting Started - Existing Projects](#getting-started---existing-projects)
  - [Getting Started - Setting Up a New Repo](#getting-started---setting-up-a-new-repo)
  - [Explore - Examine History & State](#explore---examine-history--state)
  - [Git Branching](#git-branching)
  - [Merge Conflicts](#merge-conflicts)
  - [Git More - Pushing, Pulling, & Remote Origin](#git-more---pushing-pulling--remote-origin)
  - [Advance Git](#advance-git)
  - [Git Resources](#more-git-resources)
  - [Tutorials](#tutorials)
  - [Style Guide](#style-guide)
  - [Client](#client)
  - [Repository Hosting](#repository-hosting)
  - [Self-Hosted Repository](#self-hosted-repository)
  - [Workflow](#workflow)
  - [Hook management](#hook-management)
  - [Tools](#tools)
  - [Extensions](#extensions)

## Git Commands

You can run `git help` in the terminal to learn about many of these commands at any time. `git help -a` and `git help -g` list available subcommands and
concept guides. `git help <command>` or `git help <concept>` allow you to read about a specific subcommand or concept.

`HEAD` represents your current working directory. The `HEAD` pointer can be moved to different branches, tags, or commits using `git checkout`.

The `gitignore` file allows you to control what gets committed and what doesn't, allowing you to keep your keys and passwords secure, and reducing the amount of bloat on the remote repo. You can learn more about it in the [.gitignore file](soon!) above.

## Getting Started - Existing Projects

| Command                                                           | Description                                      |
| ----------------------------------------------------------------- | ------------------------------------------------ |
| `git clone ssh://git@github.com/<username>/<repository-name>.git` | Create a local copy of a remote repo using SSH   |
| `git clone https://github.com/<username>/<repository-name>.git`   | Create a local copy of a remote repo using HTTPS |

You can also [fork](https://github.com/kpatel0170/resources/fork) repos _(create a copy of the original repo that remains on your GitHub account)_.

## Getting Started - Setting Up a New Repo

| Command                                                                 | Description                                                |
| ----------------------------------------------------------------------- | ---------------------------------------------------------- |
| `git init`                                                              | Initialize a local Git repository                          |
| `git add .`                                                             | Add all files in the working directory to the staging area |
| `git commit -m "<commit message>"`                                      | Commit your changes                                        |
| `git remote add origin git@github.com:<username>/<repository-name>.git` | Add upstream repo to publish commits at (the remote repo)  |
| `git push -u origin master`                                             | Push your changes to remote repository                     |

#### More Options For Staging Files

| Command                     | Description                                          |
| --------------------------- | ---------------------------------------------------- |
| `git add <file-name.txt>`   | Add a single file to the staging area                |
| `git add -A`                | Add all files in all directories to the staging area |
| `git rm -r <file-name.txt>` | Remove a single file (or folder)                     |
| `git rm -r . --cached`      | Remove all files recursively from staging area       |

## Explore - Examine History & State

| Command                                    | Description                          |
| ------------------------------------------ | ------------------------------------ |
| `git status`                               | See details about the current branch |
| `git show`                                 | Shows changes in committed files     |
| `git log`                                  | View changes in commit history       |
| `git log --summary`                        | View changes (detailed)              |
| `git log --oneline`                        | View changes (briefly)               |
| `git diff <source branch> <target branch>` | Preview changes before merging       |

## Git Branching

| Command                                              | Description                                  |
| ---------------------------------------------------- | -------------------------------------------- |
| `git branch`                                         | List branches (the \* is the current branch) |
| `git branch -a`                                      | List all branches (local and remote)         |
| `git branch <branch name>`                           | Create a new local branch                    |
| `git branch -d <branch name>`                        | Delete a local branch                        |
| `git push origin --delete <branch name>`             | Delete a remote branch                       |
| `git checkout -b <branch name>`                      | Create a new local branch and switch to it   |
| `git checkout -b <branch name> origin/<branch name>` | Clone a remote branch and switch to it       |
| `git branch -m <old branch name> <new branch name>`  | Rename a local branch                        |
| `git checkout <branch name>`                         | Switch to a branch                           |
| `git checkout -`                                     | Switch to the most recent branch             |
| `git checkout -- <file-name.txt>`                    | Revert your recent changes to a file         |

## Merge Conflicts

| Command                                     | Description                                                                                   |
| ------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `git merge <branch name>`                   | Merge a branch into the active branch                                                         |
| `git merge <source branch> <target branch>` | Merge a branch into a target branch                                                           |
| `git merge --abort`                         | Abort the current conflict resolution process, and attempt to reconstruct the pre-merge state |
| `git stash`                                 | Stash changes in a dirty working directory                                                    |
| `git stash clear`                           | Remove all stashed entries                                                                    |

## Git More - Pushing, Pulling, & Remote Origin

| Command                                                                           | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `git push origin <branch name>`                                                   | Push a branch to your remote repo                                                 |
| `git push -u origin <branch name>`                                                | Push changes to remote repo (and remember the branch)                             |
| `git push`                                                                        | Push changes to remote repo (only if you have previously set a remote origin)     |
| `git push origin --delete <branch name>`                                          | Delete a remote branch                                                            |
| `git pull`                                                                        | Synchronize local repo with remote repo                                           |
| `git pull origin <branch name>`                                                   | Pull changes from remote repo                                                     |
| `git fetch`                                                                       | Checks to see if there are any changes on the remote repo (does not pull changes) |
| `git fetch --prune`                                                               | Fetch all remote branch refs and delete those no longer in use                    |
| `git remote -v`                                                                   | Shows URLs of remote repositories when listing your current remote connections    |
| `git remote add origin ssh://git@github.com/<username>/<repository-name>.git`     | Add upstream repo to publish commits at (the remote repo)                         |
| `git remote set-url origin ssh://git@github.com/<username>/<repository-name>.git` | Set a repo's origin branch to SSH                                                 |

## Advance Git

_HEY! Changing your history may cause undesired side effects. You may lose data. Many of these commands cannot be undone. If you change your remote history, don't say I didn't warn you._

| Command                            | Description                                                             |
| ---------------------------------- | ----------------------------------------------------------------------- |
| `git rebase <branch>`              | Reapply commits on top of another base tip                              |
| `git rebase -i <commitID>`         | Reapply all commits from <commitID forward                              |
| `git cherry-pick <commitID>`       | Apply the changes introduced by some existing commits                   |
| `git clean -f`                     | Removes and deletes untracked files from the working tree               |
| `git clean -fd`                    | Remove all untracked directories                                        |
| `git commit --amend`               | Allows you to edit a previous commit that has not been pushed           |
| `git commit --fixup <commitID>`    | Combine new changes with an existing commit under the same name         |
| `git reset <commitID>`             | Reverts all commits after specified commit, while keeping local changes |
| `git reset --hard <commitID>`      | Reverts all history and changes back to the given commit                |
| `git reset HEAD~1`                 | Revert 1 commit (while keeping current local state)                     |
| `git push origin <branch> --force` | Deletes all your previous commits and pushes your current one           |

## More Git Resources

- [Git Docs](https://git-scm.com/doc), for those who want to dive deep into the documentation
- [Git Handbook](https://guides.github.com/introduction/git-handbook/), for those who want a quick overview
- [Visual Git CheatSheet](https://ndpsoftware.com/git-cheatsheet.html), for those who are visual learners
- [Official Printable PDF CheatSheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf), for those who need the physical copy
- [Stanford GitMagic](http://www-cs-students.stanford.edu/~blynn/gitmagic/), a plain but detailed quide to git
- [GitReady](http://gitready.com/), lets you learn git one commit at a time
- [Git Explained (Not just commands)](https://towardsdatascience.com/git-help-all-2d0bb0c31483), a brief guide including more than commands
- [Interactive Way to Learn Git Branching](https://learngitbranching.js.org/), for an enjoyable way to tackle an important concept
- [Github Student Developer Pack](https://education.github.com/pack), seriously, if you're a student you should have this
 - [Version Control with Git | Udacity](https://in.udacity.com/course/version-control-with-git--ud123)
 - [Introduction to Git and Github | YouTube](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV)
 - [LearnGitBranching](https://learngitbranching.js.org/)
 - [GIT: A Visual Git Reference](https://marklodato.github.io/visual-git-guide/index-en.html)
 - [Intoduction to Git for DataScience](https://www.datacamp.com/courses/introduction-to-git-for-data-science)
 - [Git vs Github](https://www.interviewbit.com/blog/git-vs-github/)
 - [Git Tutorial | Scaler Topics](https://www.scaler.com/topics/git/)


## Tutorials

_There are tons of learning material on the Web_

- [Try Git](https://try.github.io/) - learn Git in 15 minutes with pseudo-terminal interface
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/) - comprehensive tutorial on Git
- [Learn Version Control with Git](https://www.git-tower.com/learn/) - freemium ebook from fournova Software (makers for Tower), associated with paid video course
- [Pro Git](https://git-scm.com/book/) - free Git book, also available on paper (CC BY-NC-SA 3.0)
- [Git Real: Code School](https://www.codeschool.com/courses/git-real/) - paid training course from Code School
- [Learn Git in a Month of Lunches](https://www.manning.com/books/learn-git-in-a-month-of-lunches) - tutorial-based book by Manning Publications
- [Git How To](https://githowto.com) - step by step intro
- [Explain Git with D3](https://onlywei.github.io/explain-git-with-d3/) - Visualized few basic Git concepts using D3.js: commit, branch, checkout, reset, revert, merge, rebase, fetch, pull, push, tag
- [Making Sense of Git – A Visual Perspective](https://appendto.com/2015/06/making-sense-of-git-a-visual-perspective/) - Git from a timeline and level perspective and git commands cheatsheet grouped by functionality
- [Git Tips](https://github.com/git-tips/tips)
- [Interactive/Contextual/Visual Cheat Sheet](https://ndpsoftware.com/git-cheatsheet.html)
- [The Git Parable](http://tom.preston-werner.com/2009/05/19/the-git-parable.html) - GitHub Cofounder's Narrative-style Intro to Git Concepts
- [Git Cherry-pick and its usages](https://www.loginradius.com/blog/async/git-cherry-pick/) - A blog explaining how command git cherry-pick works.
- [The ultimate guide to <code>.gitignore</code>](https://github.com/groda/the_ultimate_gitignore_guide) All about `.gitignore`.

## Style Guide

_Style guide when you work with git_

- [Udacity Nanodegree Style Guide](https://udacity.github.io/git-styleguide/index.html)

## Client

_Git clients are available on every platform, from mainframe to your mobile device_

- [GitHub Desktop](https://desktop.github.com/) - Git Client by GitHub. works with GitHub and GitHub Enterprise seamlessly
- [SourceTree](https://www.sourcetreeapp.com/) - free (in-beer) GUI client. Windows and Mac only
- [Tower](https://www.git-tower.com/) - a popular non-free Git GUI client. Mac and Windows
- [GitKraken](https://www.gitkraken.com/) - a cross Git client for Windows, Mac & Linux. Electron based. Free for non-commercial use and paid Pro version is available.
## Repository Hosting

_People have plenty of options to host their source code_

- [GitHub](https://github.com/) - the de-facto git hosting service. Perfect integration with most external services.
    - [GitHub Cheat Sheet](https://github.com/tiimgreen/github-cheat-sheet)
    - [GitHub Browser Extensions](https://github.com/stefanbuck/awesome-browser-extensions-for-github)
- [BitBucket](https://bitbucket.org/) - well-known for its free private repository (5 user max).
- [Jetbrains Space](https://www.jetbrains.com/space/) - Jetbrains all-in-one solution for software teams, with IM, ticket tracking, source control.
- [GitLab.com](https://about.gitlab.com/gitlab-com/) - a free Git repository hosting service served by GitLab EE. Unlimited repositories and private collaborators
- [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/) - cloud service for software development formerly known as Visual Studio Team Services, Visual Studio Online and Team Foundation Service Preview
- [AWS CodeCommit](https://aws.amazon.com/codecommit/) - a SaaS service provided by Amazon Web Service on high availability infrastructure

## Self-Hosted Repository

_Or you can host the code yourselves_

- [Gitolite](https://gitolite.com/gitolite/) - a simple with fine-grained access control
- [GitHub Enterprise](https://enterprise.github.com/) - self-hosted solution provided from GitHub
- [Bitbucket Server](https://www.atlassian.com/software/bitbucket/server) - self-hosted refrom Atlassian. Good integration with JIRA and other Atlassian products
- [GitLab CE/EE](https://gitlab.com/) - a popular open-source Git (CE) with paid support option (EE).

## Workflow

_Inexpensive branching allows people adopt workflows other than the classic centralized workflow_

- [Pro Git - Distributed Workflows](https://git-scm.com/book/it/v2/Distributed-Git-Distributed-Workflows)
- [Atlassian Git Tutorial - Comparing Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows)
- [Patterns for Managing Source Code Branches](https://martinfowler.com/articles/branching-patterns.html)

### Comparing workflows

_No single workflow fits everyone's need_

- [Gitflow](https://nvie.com/posts/a-successful-git-branching-model/) - the most well-known Git workflow model
- [GitHub flow](http://scottchacon.com/2011/08/31/github-flow.html) - a simple branching model with a single master

## Hook management

_Git provide hooks at commit/push phrase, allowing integration with and code quality checking tool and Continuous Integration (CI)_

- [pre-commit](https://pre-commit.com/) - a framework for managing and maintaining multi-language pre-commit hooks from Yelp. Extensive support for multiple programming language.
- [Overcommit](https://github.com/brigade/overcommit/) - a extendable Git hook manager written with Ruby.
- [husky](https://github.com/typicode/husky) - Git hooks for Node.js, manage your hooks from your package.json


## Tools

_Various tools for daily operations_

- [awesome-git-addons](https://github.com/stevemao/awesome-git-addons) - lists more than 20 git addons including all available commands
- [gr](http://mixu.net/gr/) - a tool for managing multiple git repositories
- [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/) - a simpler, faster alternative to git-filter-branch for cleansing bad data out of your Git repository history
- [GitIgnore Collection](https://github.com/github/gitignore) - collection of gitignore files for various programming language
- [etckeeper](https://etckeeper.branchable.com/) - a collection of tools to let /etc be stored in a git repository
- [gitFS](https://www.presslabs.com/gitfs/) - a FUSE file system that fully integrates with git
- [Gitless](https://gitless.com/) - an experimental version of Git that changes some of Git's underlying concepts

## Extensions

_Git is designed for source control management. but people extend the idea and push version control to everywhere_

- [Git Large File Storage](https://git-lfs.github.com/) - practical solution for versioning large files. supported by GitHub
- [Git Virtual File System or GVFS](https://github.com/Microsoft/GVFS) - solution for managing very large Git repository while maintaining speed and efficiency of most operations. in developement by Microsoft.
- [git-annex](https://git-annex.branchable.com/) - allow managing large binaries among machines, as if operation a normal git repository. possible to creates a synchronised folder with [git-annex assistant](https://git-annex.branchable.com/assistant/).

Highly influenced from [Git Tutorial: A Comprehensive Guide](https://www.codepedia.org/udemy/git-tutorial-a-comprehensive-guide/)

> :warning: This article address git topics non-linearly. Beginner may not find this page helpful.

**Learn git, if you don't wanna see yourself sad like Hitler**
<iframe width="560" height="315" src="https://www.youtube.com/embed/CDeG4S-mJts" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Wanna learn git? Ask El Risitas**
<iframe width="560" height="315" src="https://www.youtube.com/embed/2uYeb_c8_bk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
**Just kidding, even though El Risitas found learning git difficult, you will empower yourself with *anime git superpower* if you just cross the beginning threshold**

### GIT

<iframe width="560" height="315" src="https://www.youtube.com/embed/BZr7oJyh4WM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/w3jLJU7DT5E" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Git is a DVCS(Distributed Version Control System) designed by [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds).

> Linus Torvalds is also a creator of linux kernel.

> There are three types of VCS(Version Control System): Local, Centralised, Distributed.

It stores data in a file system made up of snapshots. Each time a commit is made, git stores snapshot of the changed files. If some files are not changed in current commit, git just stores reference to the previously stored snapshot.

### States
Files inside git can reside in three states:
* **Committed** Snapshot is taken, securely stored in local database.
* **Modified** File changed, but snapshot has not taken.
* **Staged** Files flagged to be commited in next snapshot.

![states]({{site.url}}/{{site.baseurl}}/assets/replenish_git/git_1.png)

### Initial Configuaration

Upon installing git, you should identify yourself in config file.

`$ git config --global user.name "Abul"`

`$ git config --global user.email "abul@gmail.com`

You can check the config later:

```bash
$ git config user.name
liiniix
$ git config user.email
thaki240198cgc@gmail.com
```

There are other things in config you can examine:
```bash
$ git config --list
user.email=thaki240198cgc@gmail.com
user.name=liiniix
core.editor=nano
alias.lg=!git lg1
alias.lg1=!git lg1-specific --all
alias.lg2=!git lg2-specific --all
alias.lg3=!git lg3-specific --all
...
...
```
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZChtKFLiaNw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Git Workflow

![Git Workflow]({{site.url}}/{{site.baseurl}}/assets/replenish_git/git_workflow.png)
I think this tutorial is best for learning git workflow togther with corresponding commands:

<iframe width="560" height="315" src="https://www.youtube.com/embed/3a2x1iJFJWc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Tracked and Untracked Files

* **Tracked files** Tracked files are those files who were in previous snapshot, even though unmodified or modified or staged.
* **Untracked files** Untracked files are those files who were not in previous snapshot. Upon creation of new files, you introduce untracked files who requires to be tracked by command `git add`

### Tracking and Staging

For single file `git add filename`, for multiple files `git add *`.

> '*' is wildcard which is a regex for all files in current directory for current case

### Commit

When committed, git takes snapshot of all modified staged tracked files.
```bash
$ git commit -m "message"
```

### Pushing

To push changes to the remote repository in master branch:
```bash
$ git push origin master
```

### Stash

Let's say you made some changes: modified, staged, untracked. But you had to go to the latest commit freash and do some changes. But you don't wanna lose your current changes. `stash` will temporarily hides your changes and fetch you in the latest commit freash.
```bash
$ git stash
```

### Remote repository

To make collaboration with your co-workers, you have to consider remote repository. `origin` is the shortened name of your remote repository.
```bash
$ git remote
origin
$ git remote -v
origin	https://github.com/liiniix/myblog.git (fetch)
origin	https://github.com/liiniix/myblog.git (push)
```
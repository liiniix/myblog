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
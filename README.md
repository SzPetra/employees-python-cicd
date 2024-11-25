This is README file of Python project training.
This is a Python project.

--git diff: difference between the README.md file on HEAD and README.md file in local

--git blame: shows who was the last person and when did the person make changes to a commit

--git -v: check the remote repositories conected
--git remote remove origin: deletes connected origin(alias) remote repository
--git -u origin master: add remote origin(alias) repository

--git log: only show log of local repository, to check remote -> git log origin/master

--git stash: we put our changes aside 
--git stash list: checking the stashed items
--git stash pop: Ctrl + s, brings back our latest stashed item
--git stash push -m "Example": this gives it a title
--git stash drop: we delete the stashed item
--git stash apply: Ctrl + x, brings stash forward but still remains in the 
--git stash clear: delete stash list items
--git stash pop stash{1}: can bring back changes other than the latest (1 in here is the index of item in stash list)

--git checkout -b hello-world: creates hello-world branch and checks out to branch as well
--git branch: lists all available branches in respository
--git switch master: checks out to main branch

More than one remote repositories can be added (named differently, for example: origin&backup).

In GitHub there is more detailed description for commits, which is the body of the commit, should describe what happened in the commit, HEADER is just the title of it.

When using git status and "changes can be fast-forwarded" message displays, means there would be no conflict when merging the two together.
When using git status and "diverged" message displays, means when merging the two branch will have conflict.

When using git abort, (when having merge conflict) it will go back to previous state of my LOCAL repository as if I haven't pulled the changes from REMOTE.

HEAD is the last commit by Git definition.

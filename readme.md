# <https://www.freecodecamp.org/news/git-reverting-to-previous-commit-how-to-revert-to-last-commit>

feat: first commit
fix: second commit
fix: third commit

Now we have three commits. To revert to a previous commit, you must first get the commit ID. To do that, run the command below:

git log --oneline

d4ceb8f (HEAD -> master, origin/master) fix: third commit
b08fc26 fix: second commit
3db388d feat: initial commit

To go back to the second commit, you run the git reset command followed by the commit ID. That is:

git reset b08fc26

But when we run the git log --oneline command, the third commit wont't be in the log of commits:

git log --oneline

We've successfully gone back to a previous commit.

If you want to undo a commit and the all the changes made after that commit, you attach the --hard flag to your git reset command.

Let's test this out by reverting back to the first commit:

git reset 89f6c3d --hard



How to Revert to a Previous Commit Using the git revert Command
I have already initialized the project and made three commits like we did in the last section. Here's what the commit log looks like:

commit-log
git log --oneline


To revert to the to the previous commit, run the git revert command along with the commit ID of the current commit.

In our case, we'll be using the ID of the third commit:

git revert 882ad02
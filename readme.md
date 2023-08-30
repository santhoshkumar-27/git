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

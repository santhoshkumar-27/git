# <https://www.freecodecamp.org/news/git-revert-file-reverting-a-file-to-a-previous-commit/>

When working with Git, you often commit your changes and then push them to a remote repository.

Suppose you have made a lot of commits and later realize that your current version of changes is wrong. Or you discover a situation that requires you to revert to a previous commit, like a strange bug.

Manually changing each line of code in your file to its original state or a specific commit state and doing a new commit can lead to a messy commit history. Reverting the file is a much cleaner way to handle it.

There are many possible approaches, but in this article, you will learn the best approach, the git checkout method.

If you are in a rush, here is the command:

$ git checkout SHA-HASH -- file/file-path

But suppose you are not in a rush. Let’s start by first learning how to locate all previous commits and their SHA hash. Then we'll see how to revert a file to a previous commit.

How to Find the Commit SHA/ID
There are many ways to get each commit's SHA and details. The best method is to use the command below in your terminal:

$ git log

give like this

commit 593299c23b712582d38a7ece67aea19f0d8fba09 (HEAD -> master, origin/master)
Author: kaviyarasan <kaviyarasan.t@twilightitsolutions.com>
Date:   Wed Aug 30 10:34:32 2023 +0530

    fix: r

commit cf779b6e724e581947e35888613226f904948858
Author: kaviyarasan <kaviyarasan.t@twilightitsolutions.com>
Date:   Wed Aug 30 10:14:03 2023 +0530

    Revert "fix: third commit"
    
    This reverts commit d4ceb8faf84f200ddcca50fddfe8eb6baef3d424.

commit c816eb89ba2a96b59eb31c825e7baf528d2e5ad6
Author: kaviyarasan <kaviyarasan.t@twilightitsolutions.com>
Date:   Wed Aug 30 10:10:45 2023 +0530

    fix: feat

But a more straightforward command to use is the command below, where you attach the oneline option:

$ git log --oneline
Note: The oneline option displays the output as one commit per line.

Using this command alone would return all commits made on that project. If you want to revert a particular file to a previous commit, you must first see all commits made to that file.

To do this, add the file name to the command:

$ git log --oneline README.md

In a situation where the file is located in another folder, you can either navigate your terminal to the folder or use the file path in the command as seen below:

$ git log --oneline src/App.js

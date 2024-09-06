do `git reflog --no-abbrev` and find the SHA1 for the commit at the tip of your deleted branch, then just `git checkout [sha]`. O

Once you're at that commit, you can just `git checkout -b [branchname]` to recreate the branch from there.



[stack overflow original answer](https://stackoverflow.com/questions/3640764/can-i-recover-a-branch-after-its-deletion-in-git "https://stackoverflow.com/questions/3640764/can-i-recover-a-branch-after-its-deletion-in-git")

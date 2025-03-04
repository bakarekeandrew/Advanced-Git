# Git Exercises

## Advanced Git

### Part 1: Refining Git History

```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1
$ git init
Initialized empty Git repository in C:/Users/HP/Desktop/part1/.git/

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test1.md && git commit -m "chore: Create initial file"
[master (root-commit) 56c9864] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test2.md && git commit -m "chore: Create another file"
[master 5b9e0c3] chore: Create another file     
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[master 1ce708c] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)     
 create mode 100644 test3.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git status
On branch master
reword 5b9e0c3 chore: Create another file
chore: Create second file
Untracked files:
  (use "git add <file>..." to include in what will be committed)     
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
squash 4fa6ca0 chore: Create second file
$ $ git add test4.md
bash: $: command not found

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ $ git commit --amend -m "chore: Create third and fourth files"     
bash: $: command not found

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit --amend -m "chore: Create third and fourth files"       
[master 2b576dd] chore: Create third and fourth files
 Date: Tue Mar 4 10:43:40 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
[detached HEAD 4fa6ca0] chore: Create second file
 Date: Tue Mar 4 10:43:24 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
error: cannot 'squash' without a previous commit
You can fix this with 'git rebase --edit-todo' and then run 'git rebase --continue'.
Or you can abort the rebase with 'git rebase --abort'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase -i HEAD~1
fatal: It seems that there is already a rebase-merge directory, and  
I wonder if you are in the middle of another rebase.  If that is the 
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something    
valuable there.


HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase --skip
error: cannot 'squash' without a previous commit
error: please fix this using 'git rebase --edit-todo'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase --abort
pick 4fa6ca0 chore: Create second file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test3.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create third file"
On branch master
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create third file"
On branch master
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create fourth file"
On branch master
pick 687f88d chore: Create second file
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
[detached HEAD 687f88d] chore: Create second file
 Date: Tue Mar 4 10:43:24 2025 +0200
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Unwanted content" > unwanted.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Unwanted commit"
[master cedf51b] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ echo "Test 5 content" > test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch aa64d05] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git checkout master
Switched to branch 'master'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git cherry-pick ft/branch
[master 22c8ac7] Implemented test 5
 Date: Tue Mar 4 11:02:03 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git log --graph --oneline --all
* 22c8ac7 (HEAD -> master) Implemented test 5
| * aa64d05 (ft/branch) Implemented test 5
|/
* 687f88d chore: Create second file
* 56c9864 chore: Create initial file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git reflog
22c8ac7 (HEAD -> master) HEAD@{0}: cherry-pick: Implemented test 5
687f88d HEAD@{1}: checkout: moving from ft/branch to master
aa64d05 (ft/branch) HEAD@{2}: commit: Implemented test 5
687f88d HEAD@{3}: checkout: moving from master to ft/branch
687f88d HEAD@{4}: rebase (finish): returning to refs/heads/master    
687f88d HEAD@{5}: rebase (start): checkout HEAD~2
cedf51b HEAD@{6}: commit: Unwanted commit
687f88d HEAD@{7}: rebase (finish): returning to refs/heads/master    
687f88d HEAD@{8}: rebase (squash): chore: Create second file
4fa6ca0 HEAD@{9}: rebase (start): checkout HEAD~2
9b5635b HEAD@{10}: rebase (finish): returning to refs/heads/master   
9b5635b HEAD@{11}: rebase (start): checkout HEAD~1
9b5635b HEAD@{12}: rebase (abort): returning to refs/heads/master    
56c9864 HEAD@{13}: rebase (start): checkout HEAD~2
9b5635b HEAD@{14}: rebase (finish): returning to refs/heads/master   
9b5635b HEAD@{15}: rebase (pick): chore: Create third and fourth files
4fa6ca0 HEAD@{16}: rebase (reword): chore: Create second file        
5b9e0c3 HEAD@{17}: rebase: fast-forward
56c9864 HEAD@{18}: rebase (start): checkout HEAD~2
2b576dd HEAD@{19}: commit (amend): chore: Create third and fourth files
1ce708c HEAD@{20}: commit: chore: Create third and fourth files      
5b9e0c3 HEAD@{21}: commit: chore: Create another file
56c9864 HEAD@{22}: commit (initial): chore: Create initial file      

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git reset --hard
HEAD is now at 22c8ac7 Implemented test 5

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git remote add origin https://github.com/bakarekeandrew/Advanced-git.git

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push -u origin master
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (8/8), 691 bytes | 22.00 KiB/s, done.
Total 8 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)        
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/bakarekeandrew/Advanced-git.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```

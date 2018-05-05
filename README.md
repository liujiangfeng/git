# git
test_git


Last login: Sat May  5 02:08:24 on console
TEFFYLIU-MB0:~ liu$ def
defaults   defragcli
TEFFYLIU-MB0:~ liu$ def
defaults   defragcli
TEFFYLIU-MB0:~ liu$ defaults write com.apple.finder AppleShowAllFiles TRUE
TEFFYLIU-MB0:~ liu$ killall Finder
TEFFYLIU-MB0:~ liu$ git branch
fatal: Not a git repository (or any of the parent directories): .git
TEFFYLIU-MB0:~ liu$ cd code/git_test/
TEFFYLIU-MB0:git_test liu$ cd git
TEFFYLIU-MB0:git liu$ git branch
* master
TEFFYLIU-MB0:git liu$ git branch
* dev
  master
TEFFYLIU-MB0:git liu$ ls
README.md b.txt   d.txt
a.txt   c.txt   e.txt
TEFFYLIU-MB0:git liu$ touch f.txt
TEFFYLIU-MB0:git liu$ subl f.txt
TEFFYLIU-MB0:git liu$ git add f.txt
TEFFYLIU-MB0:git liu$ git commit -m 'add file '
[dev ea5a951] add file
 1 file changed, 1 insertion(+)
 create mode 100644 f.txt
TEFFYLIU-MB0:git liu$ git push
fatal: The current branch dev has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin dev

TEFFYLIU-MB0:git liu$ more .git/
.DS_Store       ORIG_HEAD       hooks/          logs/
COMMIT_EDITMSG  branches/       index           objects/
FETCH_HEAD      config          info/           packed-refs
HEAD            description     lfs/            refs/
TEFFYLIU-MB0:git liu$ more .git/branches/
.git/branches/ is a directory
TEFFYLIU-MB0:git liu$ ls .git/branches/
TEFFYLIU-MB0:git liu$
TEFFYLIU-MB0:git liu$ ls .git/branches/
TEFFYLIU-MB0:git liu$ git log
commit ea5a95127a8731e9c7e56b1e531bf5c6bf49473f (HEAD -> dev)
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 21:24:56 2018 +0800

    add file

commit 7936f4261b481ec43e0077bc10c6387a65057dec (origin/master, origin/HEAD, master)
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 14:41:44 2018 +0800

    submit

    submit

commit bc8287fb3b064f45542bbd9813999a46629c5299
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 01:19:39 2018 +0800

    aaa

commit 969d9ede7934bc87ffe58080e06983b9f271ca73
Merge: 1d2cd7a 68453f0
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 01:08:40 2018 +0800

    Merge branch 'master' of github.com:liujiangfeng/git
Merge: 1d2cd7a 68453f0
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 01:08:40 2018 +0800

    Merge branch 'master' of github.com:liujiangfeng/git

commit 1d2cd7a3b50fdc14e6a0cde2dbd2c4f090445f7e
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 01:07:00 2018 +0800

    c.text

commit 68453f0c75a0332595d68b27e37ac2711ffee1fc
Author: jiangfeng <liujiangfeng16@126.com>
Date:   Sat May 5 01:06:26 2018 +0800

    Create b.txt

commit b6471e26aacad50841cc1a601916219161314049
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 00:56:34 2018 +0800

    kjfkdkfjkdfj

commit 2e7661064606407f8f77bc55387f0e539302a807
Author: jiangfeng <liujiangfeng16@126.com>
Date:   Sat May 5 00:25:58 2018 +0800

    Initial commit
TEFFYLIU-MB0:git liu$ git status
On branch dev
nothing to commit, working tree clean
TEFFYLIU-MB0:git liu$ git branch
* dev
  master
TEFFYLIU-MB0:git liu$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
TEFFYLIU-MB0:git liu$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
TEFFYLIU-MB0:git liu$ git branch
  dev
* master
TEFFYLIU-MB0:git liu$ ls
README.md b.txt   d.txt
a.txt   c.txt   e.txt
TEFFYLIU-MB0:git liu$ git checkout dev
Switched to branch 'dev'
TEFFYLIU-MB0:git liu$ git checkout -b bug11
Switched to a new branch 'bug11'
TEFFYLIU-MB0:git liu$ git branch
* bug11
  dev
  master
TEFFYLIU-MB0:git liu$ cat .git/refs/heads/
cat: .git/refs/heads/: Is a directory
TEFFYLIU-MB0:git liu$ cat .git/refs/heads/
bug11   dev     master
TEFFYLIU-MB0:git liu$ cat .git/refs/heads/
bug11   dev     master
TEFFYLIU-MB0:git liu$ cat .git/HEAD
.DS_Store  README.md  b.txt      d.txt      f.txt
.git/      a.txt      c.txt      e.txt
TEFFYLIU-MB0:git liu$ cat .git/HEAD
ref: refs/heads/bug11
TEFFYLIU-MB0:git liu$ git checkout dev
Switched to branch 'dev'
TEFFYLIU-MB0:git liu$ cat .git/HEAD
ref: refs/heads/dev
TEFFYLIU-MB0:git liu$ git log --oneline --all --decorate
ea5a951 (HEAD -> dev, bug11) add file
7936f42 (origin/master, origin/HEAD, master) submit
bc8287f aaa
969d9ed Merge branch 'master' of github.com:liujiangfeng/git
1d2cd7a c.text
68453f0 Create b.txt
b6471e2 kjfkdkfjkdfj
2e76610 Initial commit
TEFFYLIU-MB0:git liu$ git log --oneline --all --decorate --graph
* ea5a951 (HEAD -> dev, bug11) add file
* 7936f42 (origin/master, origin/HEAD, master) submit
* bc8287f aaa
*   969d9ed Merge branch 'master' of github.com:liujiangfeng/git
|\
| * 68453f0 Create b.txt
* | 1d2cd7a c.text
|/
* b6471e2 kjfkdkfjkdfj
* 2e76610 Initial commit
TEFFYLIU-MB0:git liu$ pwd
/Users/liu/code/git_test/git
TEFFYLIU-MB0:git liu$ cd ../
TEFFYLIU-MB0:git_test liu$ cd ../
TEFFYLIU-MB0:code liu$ mkdir git_init
TEFFYLIU-MB0:code liu$ cd git_init/
TEFFYLIU-MB0:git_init liu$ git init
Initialized empty Git repository in /Users/liu/Code/git_init/.git/
TEFFYLIU-MB0:git_init liu$ git log --oneline --all --decorate --graph
TEFFYLIU-MB0:git_init liu$ touch init
TEFFYLIU-MB0:git_init liu$ git add init
TEFFYLIU-MB0:git_init liu$ git commit -m 'add init'
[master (root-commit) 96a57ab] add init
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 init
TEFFYLIU-MB0:git_init liu$ git log --oneline --all --decorate --graph
* 96a57ab (HEAD -> master) add init
TEFFYLIU-MB0:git_init liu$ git config --global alias.logg 'log --oneline --all --decorate --graph'
TEFFYLIU-MB0:git_init liu$ git logg
* 96a57ab (HEAD -> master) add init
TEFFYLIU-MB0:git_init liu$ git config --global alias.co checkout
TEFFYLIU-MB0:git_init liu$ git co -b a_branch master
Switched to a new branch 'a_branch'
TEFFYLIU-MB0:git_init liu$ git logg
* 96a57ab (HEAD -> a_branch, master) add init
TEFFYLIU-MB0:git_init liu$ git branch
* a_branch
  master
TEFFYLIU-MB0:git_init liu$ touch a
TEFFYLIU-MB0:git_init liu$ git add
Nothing specified, nothing added.
Maybe you wanted to say 'git add .'?
TEFFYLIU-MB0:git_init liu$ git add .
TEFFYLIU-MB0:git_init liu$ git commit -m 'add a file'
[a_branch 6befe54] add a file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a
TEFFYLIU-MB0:git_init liu$ git log
commit 6befe5401a3203cef5fa80413efa25762d57ece8 (HEAD -> a_branch)
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 22:18:47 2018 +0800

    add a file

commit 96a57abaa1d820f5c374d2675b9057ffb79aac4c (master)
Author: teffyliu <liujiangfeng16@126.com>
Date:   Sat May 5 22:14:08 2018 +0800

    add init
TEFFYLIU-MB0:git_init liu$ git logg
* 6befe54 (HEAD -> a_branch) add a file
* 96a57ab (master) add init
TEFFYLIU-MB0:git_init liu$ git co -b b_branch master
Switched to a new branch 'b_branch'
TEFFYLIU-MB0:git_init liu$ git branch
  a_branch
* b_branch
  master
TEFFYLIU-MB0:git_init liu$ git logg
* 6befe54 (a_branch) add a file
* 96a57ab (HEAD -> b_branch, master) add init
TEFFYLIU-MB0:git_init liu$ touch b
TEFFYLIU-MB0:git_init liu$ git add .
TEFFYLIU-MB0:git_init liu$ git commit -m 'add b file'
[b_branch 5fcb323] add b file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 b
TEFFYLIU-MB0:git_init liu$ git logg
* 5fcb323 (HEAD -> b_branch) add b file
| * 6befe54 (a_branch) add a file
|/
* 96a57ab (master) add init
TEFFYLIU-MB0:git_init liu$ git logg
* 5fcb323 (b_branch) add b file
| * 6befe54 (HEAD -> a_branch) add a file
|/
* 96a57ab (master) add init
TEFFYLIU-MB0:git_init liu$ git co b_branch
Switched to branch 'b_branch'
TEFFYLIU-MB0:git_init liu$
## tag Means: 
	2.5.23
	 - 2: 表示大版本
	 - 5: 表示新加的功能
	 - å23: 表示 bug 的修复

#### Check Git config list

```
<Aaron>PT:FirstDemo$ git config --global --list
	filter.lfs.clean=git-lfs clean -- %f
	filter.lfs.smudge=git-lfs smudge -- %f
	filter.lfs.process=git-lfs filter-process
	filter.lfs.required=true
	user.name=Aaron
	user.email=2294966591@qq.com
	http.postbuffer=524288000
	http.sslverify=false
	core.compression=-1
	core.excludesfile=~/.gitignore_global
	safe.directory=/usr/local/Homebrew/Library/Taps/homebrew/homebrew-core
	safe.directory=/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask
```



### Config Username & email & store setting

```
<Aaron>PT:FirstDemo$ git config --global user.name "HallowAaron"
<Aaron>PT:FirstDemo$ git config --global user.email "2294966591@qq.com"
<Aaron>PT:FirstDemo$ git config --global credential.helper store
```





# [Start](https://www.youtube.com/watch?v=PN1k1CLXtlw&t=3166s)



### 1. Create Repository 

```
Method 1:
	- git init
Method 2:
	- git clone xxx
```

```
<Aaron>PT:LearnGit$ git init
Initialized empty Git repository in /Users/aaron/Aaron/SelfStudy/GitHub/Project/LearnGit/.git/
<Aaron>PT:LearnGit$ ls
<Aaron>PT:LearnGit$ ls -al
total 0
drwxr-xr-x  3 aaron  staff   96 Oct 18 16:10 .
drwxr-xr-x  5 aaron  staff  160 Oct 18 16:09 ..
drwxr-xr-x  9 aaron  staff  288 Oct 18 16:10 .git
<Aaron>PT:LearnGit$ cd ./.git/
<Aaron>PT:.git$ ls -altr
total 24
drwxr-xr-x   3 aaron  staff   96 Oct 18 16:10 ..
drwxr-xr-x   3 aaron  staff   96 Oct 18 16:10 info
-rw-r--r--   1 aaron  staff   73 Oct 18 16:10 description
drwxr-xr-x  15 aaron  staff  480 Oct 18 16:10 hooks
drwxr-xr-x   4 aaron  staff  128 Oct 18 16:10 refs
-rw-r--r--   1 aaron  staff   21 Oct 18 16:10 HEAD
-rw-r--r--   1 aaron  staff  137 Oct 18 16:10 config
drwxr-xr-x   9 aaron  staff  288 Oct 18 16:10 .
drwxr-xr-x   4 aaron  staff  128 Oct 18 16:10 objects
<Aaron>PT:.git$ cd ..
<Aaron>PT:LearnGit$ git init my-repo
Initialized empty Git repository in /Users/aaron/Aaron/SelfStudy/GitHub/Project/LearnGit/my-repo/.git/
<Aaron>PT:LearnGit$ ls 
my-repo

```

- **git init**
  - if not add nothing string, it means at current folder create a folder, named: .git
- **git init my-repo**
  - it means, create a ***.git*** folder at ***my-repo*** folder



**Git Repository:**

- Working Directory
- Staging Area/Index
- Local respository

<img src="/Users/aaron/Aaron/SelfStudy/GitHub/Project/LearnGit/Git_Responsitory.png"/>





**Git Relationship:**

- **Untrack**: new create file, not recognized by git
- **Unomfided**: recognized by git, but file content no changing 
- **Modified**: file content already modified, but not add to git buffer
- **Staged**: file already add at git buffer

<img src="/Users/aaron/Aaron/SelfStudy/GitHub/Project/LearnGit/git_relationship.png">





**Add Code to local repository**

```
1. git init: 
	Create repository 
2. git status: 
	check repository status
3. git add: 
	add file to git buffer
4. git commit: 
	submit 
```



```
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git_Usage.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_relationship.png

<Aaron>PT:LearnGit$ git add git_relationship.png
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git_Usage.md

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

<Aaron>PT:LearnGit$ git add git_relationship.png
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git_Usage.md

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

<Aaron>PT:LearnGit$ git rm  git_relationship.png
error: the following file has changes staged in the index:
    git_relationship.png
(use --cached to keep the file, or -f to force removal)
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git_Usage.md

<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git_Usage.md
	deleted:    git_relationship.png

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_relationship.png

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

<Aaron>PT:LearnGit$ git rm git_relationship.png
error: the following file has changes staged in the index:
    git_relationship.png
(use --cached to keep the file, or -f to force removal)
<Aaron>PT:LearnGit$ git rm -r git_relationship.png
error: the following file has changes staged in the index:
    git_relationship.png
(use --cached to keep the file, or -f to force removal)
<Aaron>PT:LearnGit$ git git_relationship.png git_relationship.png
git: 'git_relationship.png' is not a git command. See 'git --help'.
<Aaron>PT:LearnGit$ git --cached git_relationship.png
unknown option: --cached
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]
<Aaron>PT:LearnGit$ git rm --cached git_relationship.png
rm 'git_relationship.png'
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_relationship.png

<Aaron>PT:LearnGit$ git rm -f git_relationship.png
fatal: pathspec 'git_relationship.png' did not match any files
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_relationship.png

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git rm -f git_relationship.png
rm 'git_relationship.png'
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_relationship.png

<Aaron>PT:LearnGit$ git add .
<Aaron>PT:LearnGit$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .DS_Store
	new file:   Git_Responsitory.png
	new file:   Git_Usage.md
	new file:   git_relationship.png

<Aaron>PT:LearnGit$ git commit -m "first commit"
[main (root-commit) f1b614d] first commit
 4 files changed, 183 insertions(+)
 create mode 100644 .DS_Store
 create mode 100644 Git_Responsitory.png
 create mode 100644 Git_Usage.md
 create mode 100644 git_relationship.png
<Aaron>PT:LearnGit$ git status
On branch main
nothing to commit, working tree clean 
```






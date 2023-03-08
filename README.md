# ayao-git-note
[gitlab flavored markdown](https://docs.gitlab.com/ee/user/markdown.html)

[github wiki]

[github action]

[git flight rules](https://github.com/k88hudson/git-flight-rules/blob/master/README.md)

[.gitignore](https://github.com/github/gitignore)

[git document](https://git-scm.com)

[github profile readme]()

<p align="center">
    <img width="200" src="https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png">
</p>

<h1 align="center">Git学习记录</h1>

<div align="center">
    「从入门到入土 」
</div>

## why do we need VCS(Version Control System)? 

***also known as SCM (Source Code Management) tools or RCS (Revision Control System)***

Allow me show you how work will be done without VCS?

perhaps with postfixed like "final" or "modified" and then had to later deal with a new final version. 
  
Perhaps you've commented out code blocks because you want to disable certain functionality without deleting the code,
fearing that there may be a use for it later. Version control is a way out of these problems
disk_usuage_fixed.py
disk_usage_final.py
disk_usage_original.py

 It's a place where I can work without constantly worrying about making a mistake. It's a place where I can work without having to be too careful. 
 It's a place where I can experiment with ideas that may not work out. 
 I wish I had working folders everywhere if I accidentally put too much pepper on this meal, I can just revert to the latest version in the repository.
 
`version control is design to solve problem like this`
keep track of  file status
- rename `disk_usage.py` to `free_memory.py`






## iteract with git

## iteract with github

## Git state management mechanisms 


### review and revisit any commit in the history
```

#By default, git log will only show commits for the currently selected branch
git log 
#view all commits across all branches
git log --branches=*

```
what really happen behind the checkout command
```
During the normal course of development, the HEAD usually points to main or some other local branch, but when you check out a previous commit, HEAD no longer points to a branch—it points directly to a commit. This is called a “detached HEAD” state,
```


## undo the change in commit history

`git revert`command in most use way
```
#  create a new commit with the inverse of the last commit
>git revert Head
>git log --oneline
e2f9a78 Revert "New name for disk_usage.py"
872fa7e New name for disk_usage.py

# what happen under the hood?
Although 872fa7e still exists in the history, the new e2f9a78 commit is an inverse of the changes in 872fa7e
```

`git reset`command in most use way
```diff
#reset to that specified commit
>git reset --hard a1e8fb5
>git log --oneline
- e2f9a78 Revert "New name for disk_usage.py"
- 872fa7e New name for disk_usage.py 
+ a1e8fb5 Allow printing more than one error message
+ 435b61d Iterate over a list of checks and messages to avoid code duplication

`what happened under the hood`
The log output shows the e2f9a78 and 872fa7e commits no longer exist in the commit history.
`situation that you should avoid ues reset command to do the job`
If we have a shared remote repository that has the 872fa7e commit pushed to it, and we try to git push a branch where we have reset the history, Git will catch this and throw an error. Git will assume that the branch being pushed is not up to date because of it's missing commits
```


`git ammend` command  in most use way
```
`case simulation:amend the last commit`

## edit check_disk_free.py

# staged all file in current directroy
git add .

# commit the changes in the stage
git commit -m "Add check_disk_free.py"

# relaize forget to commit check_network_ok.py 
# staged them for commit by using git add
git add .
# amend the changes in last commit
git commit --amend -m "Amend the check_disk_free.py"
```

```
# 编辑了hello.py和main.py

# 缓存了目录下所有文件
git add .

# 意识到hello.py和main.py中的修改
# 应该在不同的快照中提交

# 取消main.py缓存
git reset main.py

# 只提交hello.py
git commit -m "Make some changes to hello.py"

# 在另一份快照中提交main.py
git add main.py
git commit -m "Edit main.py"
```
## undo the change in workingbench
git clean command in most use way

## undo the change in romote repositroy


## remove untracked file - `git clean` command

**Initialize demo repository with tracked and untrack changes**
```
mkdir git_clean_test
$ cd git_clean_test/
$ git init .
Initialized empty Git repository in /Users/kev/code/git_clean_test/.git/
$ echo "tracked" > ./tracked_file
$ git add ./tracked_file
$ echo "untracked" > ./untracked_file
$ mkdir ./untracked_dir && touch ./untracked_dir/file
$ git status
On branch master

Initialize commit

Changes to be committed: (use "git rm --cached <file>..." to unstage)

new file: tracked_file

Untracked files: (use "git add <file>..." to include in what will be committed) untracked_dir/ untracked_file
```
**essential and detachable component lexcial item**
`git clean <option> <path> `

**Default behaviour of `git clean` command**
>remove untracked file in the current directory
>defalut provide info：command hint
>The clean.requireForce configuration option is set to True



**most use command line option**

`git clean -f`

> a < path > value `git clean -f <path>` can be passed with the -f option that will remove a specific file

> By default git clean -f will operate on all the current directory untracked files

`git clean -d`

> The -d option tells git clean that you also want to include any untracked directories, by default it will ignore directories

`git clean -x`

> The -x option tells git clean to also include any ignored files.

`git clean -n`

>it is a best practice to execute a 'dry run' first, before the final deletion.

`git clean -i`

>start an interactive clean session
```$ git clean -di
Would remove the following items:
  untracked_dir/  untracked_file
*** Commands ***
    1: clean                2: filter by pattern    3: select by numbers    4: ask each             5: quit                 6: help
What now>
```
**What really happen under the hood**


## branch and merge
** most seen created branch in software devlopment workflow**
- "dev" (stuff that is in active development)
- "test" (stuff that is being tested) 
- "rel" (stuff that is ready for production release)
- "fix"

** most seen created work directory in softeware devlopment workflow**
- "bulid" (contain  file postfix like .dll which generated by source code
- "distribution"
- 




移除当前目录下未被跟踪的文件
它不会删除 .gitignore 中指定的未跟踪的文件
breadcrumb
# DVCS（Distributed Version Control System）
# CVS (Central Version Control System)
# flight rules
https://github.com/k88hudson/git-flight-rules/blob/master/README_zh-CN.md#编辑提交editting-commits



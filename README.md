# ayao-git-note
[github flavored markdown](https://github.github.com/gfm/)

[git flight rules](https://github.com/k88hudson/git-flight-rules/blob/master/README.md)

[.gitignore](https://github.com/github/gitignore)

[git document](https://git-scm.com)

<p align="center">
    <img width="200" src="https://ibb.co/FzRwKds">
</p>

<h1 align="center">Git学习记录</h1>

<div align="center">
    「从入门到入土 」
</div>

## why do we need VCS(Version Control System)? 

```also known as SCM (Source Code Management) tools or RCS (Revision Control System)```

Allow me show you work will be done without VCS

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
keep track change history of every file
- rename `disk_usage.py` to `free_memory.py`
branch and merge
- "dev" (stuff that is in active development)
- "test" (stuff that is being tested) 
- "rel" (stuff that is ready for production release)
- "bug fix"
- 
![](https://wac-cdn.atlassian.com/dam/jcr:07a92202-d02b-4875-bb8a-e138cd7b26f1/version-control.svg?cdnVersion=825)
breadcrumb
# DVCS（Distributed Version Control System）
# CVS (Central Version Control System)
# flight rules
https://github.com/k88hudson/git-flight-rules/blob/master/README_zh-CN.md#编辑提交editting-commits


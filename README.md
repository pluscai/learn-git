> GIT NOTES
# 1.Getting Started
## 1.7 Getting Help
```
$ git help <verb>
$ git <verb> --help

$ git <verb> -h

eg1: this will open a manpage in your browser about all about `git config`
$ git help config
$ git config --help

eg2: if you just need a quick refresher for current command,use `-h` option
$ git add -h
```

# 2.Git Basics
## 2.2 Recording Changes to the Repository(over)
### Committing Your Changes
> Remember that the commit records the snapshot you set up in your staging area.  Anything you didn’t stage is still sitting there modified; you can do another commit to add it to your history.

### Skipping the Staging Area
```
git commit -a -m"" => git add All  +  git commit -m""
```

### Removing Files

- `git rm` : The `git rm` command does that, and also removes the file from your working directory
- `git rm --cached xx`:   keep the file on your hard drive but not have Git track it anymore

### Moving Files

```
$ git mv file_from file_to
=>  this command is same to 
$ mv README.md README
$ git rm README.md
$ git add README
```

## 2.3 Viewing the Commit History

`git log`的两类操作：

1. 展示log的方式不一样：eg：`git log --oneline`
2. 对输出的log进行筛选：可按照时间、条数，甚至可以针对某个文件夹打印log日志

## 2.4 Undoing Things(撤销)

撤销涉及两种情况：

1. 已提交：要撤销已经提交的修改用`git commit --amend` 会用新提交覆盖之前的提交
2. 未提交的：根据命令行`git status` 即可看到如何撤销
   - 已添加进暂存区的： `git restore --staged文件名`  从暂存区中移除
   - 未添加进暂存区，撤销本地文件的修改：`git restore 文件名`（有的版本是`git checkout 文件名`）
## Git

- Clone 远程仓库中的某条分支

```sh
git init

# -t 仅跟踪远程仓库中的某条分支
# -f 添加完远程信息后立刻执行 fetch
git remote add -t <BRANCH> -f origin <REMOTE_REPO>
git checkout <BRANCH>
```

- 创建一个新的空的分支

```sh
# 创建并切换到一个空的分支
git checkout --orphan newroot

# 清除所有已跟踪的文件
git rm --cached -r .

# 清除没有进行 git add 的文件
# -n 显示将要删除的文件和目录
# -f 删除文件
# -d 删除目录
git clean -df
```

- Rebase

```sh
git rebase [-i | --interactive] [options] [--exec <cmd>] [--onto <newbase>] [<upstream>] [<branch>]
git rebase [-i | --interactive] [options] [--exec <cmd>] [--onto <newbase>] --root [<branch>]
git rebase --continue | --skip | --abort | --edit-todo
```

实际上，在 rebase 之前的提交会以 ORIG_HEAD 之名存留。如果 rebase 之后无法复原到原先的状态，可以用 `git reset --hard ORIG_HEAD` 复原到 rebase 之前的状态。
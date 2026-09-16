# Git Notecard / Git 小卡片

## 1. Uploading / 上传

```bat
git status
```
Check working directory / 工作区 and staging area / 暂存区.

```bat
git add README.md
git add notebooks/01a_mlp_hd_decoder_L1L2regularization.ipynb
git add .
```
Stage changes / 暂存更改. `git add .` stages everything under the current folder.

```bat
git commit -m "Update decoder notebook"
```
Create a local snapshot / 创建本地提交快照.

```bat
git push
```
Upload local commits / 上传本地提交 to GitHub / GitHub 远程仓库.

```bat
git push -u origin main
```
First push / 第一次推送 for a branch / 分支; sets upstream / 设置上游分支.

## 2. Fetching And Pulling / 获取与拉取

```bat
git fetch
```
Download remote information / 下载远程信息 without changing files.

```bat
git status
```
After fetch / 获取后, check whether local branch / 本地分支 is behind GitHub / GitHub.

```bat
git log --oneline HEAD..origin/main
```
Show commits on GitHub / GitHub 上有但本地没有的提交.

```bat
git pull
```
Fetch / 获取 plus merge / 合并. Updates your local branch and working files.

## 3. Inspecting And Comparing / 检查与比较

```bat
git log --oneline
```
Show compact commit history / 简洁提交历史.

```bat
git diff
```
Show unstaged changes / 未暂存更改.

```bat
git diff --staged
```
Show staged changes / 已暂存更改 that will go into the next commit.

```bat
git diff HEAD
```
Show all changes since latest commit / 当前提交以来的所有更改.

```bat
git remote -v
```
Show GitHub remote URLs / 查看远程仓库地址.

```bat
git branch
```
List branches / 查看分支.

```bat
git switch main
```
Switch branch / 切换分支.

```bat
git switch -c feature/my-experiment
```
Create and switch to a new branch / 创建并切换到新分支.

```bat
git restore --staged FILE
```
Unstage a file / 从暂存区移除文件, keeping edits.

```bat
git restore FILE
```
Discard uncommitted edits / 丢弃未提交更改. Use carefully / 小心使用.

```bat
git tag -a v0.1-initial-mlp -m "Initial working MLP decoder"
git push origin v0.1-initial-mlp
```
Create and upload a tag / 创建并上传标签.


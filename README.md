# test-repo-main

## 1 Git Subtree Usage

### 1.1 ADD & PULL

**引入**一个仓库作为 subtree

```shell
git subtree add --prefix system https://github.com/Zeal-Creations/test-repo-subtree main --squash
```

从源仓库**更新** subtree 内容

```shell
git subtree pull --prefix ./system https://github.com/Zeal-Creations/test-repo-subtree main --squash
```

要点：

- system 文件夹在操作前无需存在
- 请勿使用 `./system` 这样的路径写法， 会报错 `error: invalid path './system/README.md'`
- 如果 `add` 操作的时候使用了 `--squash`，那么在后续 pull 的时候也需要加上，不然会报错 `fatal: refusing to merge unrelated histories`
- 可以使用 `git remote add` 可以缩短命令长度，详见参考资料

### 1.2 UPDATE

```shell
git add .
git commit -m "xxx"
git subtree push --prefix=system git@github.com:Zeal-Creations/test-repo-subtree.git main
```

也可以先推到其它分支再提 `merge request` 到主分支

## 2 Reference

- [Git subtree: the alternative to Git submodule](https://www.atlassian.com/git/tutorials/git-subtree)

# test-repo-main

## 使用 Git Subtree

引入一个仓库作为 subtree

```shell
git subtree add --prefix system https://github.com/Zeal-Creations/test-repo-subtree main --squash
```

从源仓库更新 subtree 内容

```shell
git subtree pull --prefix ./system https://github.com/Zeal-Creations/test-repo-subtree main --squash
```

要点：

- system 文件夹在操作前无需存在
- 请勿使用`./system`这样的路径写法， 会报错 `error: invalid path './system/README.md'`
- 如果`add`操作的时候使用了`--squash`，那么在后续 pull 的时候也需要加上，不然会报错 `fatal: refusing to merge unrelated histories`

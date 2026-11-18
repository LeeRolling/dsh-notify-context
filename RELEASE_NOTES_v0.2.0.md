# v0.2.0 — 改名 `dsh-notify-context`

这一版**没有功能改动**，只有一件事：**换名字**。

## 为什么改

`dsh-plugin-desktop-notify` 这个名字在生态里已经撞车了：

- **npm 上被占了**：`dsh-plugin-desktop-notify` 已被他人发布（0.6.5），我们从 0.1.0 起一直没能发 npm；
- **GitHub 上有 4 个同名仓库**（其中 `owenwei888-boop/dsh-plugin-desktop-notify` 建于 2026-08-16，比本项目更早）；
- **插件市场按包名索引**：市场里显示的 `dsh-plugin-desktop-notify` 指向的是别人的包，本插件因此从未被市场收录。

继续用旧名，等于让每个用户都有装错别人的包的风险。所以改用 **`dsh-notify-context`** ——
这个名字也更贴合它跟同类插件最大的差异：**按上下文区分通知类型并给出任务摘要**。

## 变更

| 项 | 旧值 | 新值 |
|---|---|---|
| npm 包名 | `dsh-plugin-desktop-notify` | **`dsh-notify-context`** |
| GitHub 仓库 | `LeeRolling/dsh-plugin-desktop-notify` | **`LeeRolling/dsh-notify-context`**（旧链接 301 重定向） |
| 版本 | 0.1.0 | **0.2.0** |
| bundle 行 name / 客户端 bundle id | `dsh-plugin-desktop-notify` | `dsh-notify-context` |

功能、行为、诊断通道、测试**全部不变**（两套测试 30 项断言照旧）。

## 升级方式

```sh
dsh plugin --profile desktop remove dsh-plugin-desktop-notify
dsh plugin --profile desktop add github:LeeRolling/dsh-notify-context
```

然后重启客户端。旧名与新名是同一个代码库，装新版后历史配置不受影响。

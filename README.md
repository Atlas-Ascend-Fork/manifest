# CANN manifest 仓库

## 项目简介

本仓库是 CANN 的 **manifest 配置仓库**，用于通过 `repo` 工具管理和同步 CANN 相关的多个代码仓，定义 CANN 组件的仓库地址、分支版本和目录结构。

通过本 manifest，开发者可以一键初始化和同步 CANN 相关源码仓，统一管理核心运行时、算子库等多个子仓库，确保各组件版本兼容且易于维护。

- **开源代码仓库仓库**: [https://gitcode.com/cann](https://gitcode.com/cann)

---

## 快速开始

### 环境准备

先安装 Git、[Repo 工具](https://source.android.com/docs/setup/start)和 [Git LFS](https://git-lfs.com/)。本 manifest 包含使用 Git LFS 管理图片等文件的组件；下方 HTTPS 示例也会运行 `git lfs pull`。安装后执行：

```bash
repo version
git lfs version
git lfs install
```

前两条命令应能显示版本号，再继续执行下面的同步步骤。

### 1. 获取 CANN 主干代码

#### 方式一：SSH（推荐）

需先注册 SSH 公钥，参考 [GitCode SSH 配置指南](https://docs.gitcode.com/docs/help/home/user_center/security_management/ssh)

```bash
mkdir cann && cd cann
repo init -u git@gitcode.com:cann/manifest.git -b master --no-repo-verify
repo sync -c --no-tags -j12
```

#### 方式二：HTTPS

```bash
mkdir cann && cd cann
repo init -u https://gitcode.com/cann/manifest.git -b master --no-repo-verify
repo sync -c
repo forall -c 'git lfs pull'
```

---

### 2. 获取 CANN 开发分支代码

#### 方式一：SSH（推荐）

```bash
mkdir cann && cd cann
repo init -u git@gitcode.com:cann/manifest.git -b master --no-repo-verify
repo sync -c --no-tags -j12
```

#### 方式二：HTTPS

```bash
mkdir cann && cd cann
repo init -u https://gitcode.com/cann/manifest.git -b master --no-repo-verify
repo sync -c --no-tags -j12
```

## 常见问题

### 同步失败怎么办？

1. 检查网络连接
2. 确认 SSH 公钥已正确配置
3. 尝试减少并发数：`-j4` 或 `-j1`

### 如何验证同步完成？

```bash
repo status
```

---

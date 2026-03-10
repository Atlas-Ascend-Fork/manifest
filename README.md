# CANN Manifest 仓库

> CANN（Compute Architecture for Neural Networks）是华为针对 AI 场景推出的异构计算架构

## 项目简介

CANN 架构对上支持多种 AI 框架，对下服务 AI 处理器与编程，发挥承上启下的关键作用，是提升昇腾 AI 处理器计算效率的关键平台。

- **官方仓库**: [https://gitcode.com/cann](https://gitcode.com/cann)
- **文档中心**: [https://gitcode.com/cann](https://gitcode.com/cann)

---

## 快速开始

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
repo init -u git@gitcode.com:cann/manifest.git -b master --no-repo-verify -m cann-dev.xml
repo sync -c --no-tags -j12
```

#### 方式二：HTTPS

```bash
mkdir cann && cd cann
repo init -u https://gitcode.com/cann/manifest.git -b master --no-repo-verify -m cann-dev.xml
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

## 许可证

请参考各子仓库的 LICENSE 文件。

---
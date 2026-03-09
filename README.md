# README

## CANN项目

CANN（Compute Architecture for Neural Networks）是华为针对AI场景推出的异构计算架构，对上支持多种AI框架，对下服务AI处理器与编程，发挥承上启下的关键作用，是提升昇腾AI处理器计算效率的关键平台。

开源代码仓库地址：[https://gitcode.com/cann](https://gitcode.com/cann)。

## 操作步骤

- **CANN主干代码获取**

  方式一（推荐）：通过repo + ssh下载（需注册公钥，请参考[GitCode帮助中心](https://docs.gitcode.com/docs/help/home/user_center/security_management/ssh)）。

  ```
  mkdir cann
  cd cann
  repo init -u git@gitcode.com:cann/manifest.git -b master --no-repo-verify
  repo sync -c --no-tags -j12
  ```

  方式二：通过repo + https下载。

  ```
  mkdir cann
  cd cann
  repo init -u https://gitcode.com/cann/manifest.git -b master --no-repo-verify
  repo sync -c
  repo forall -c 'git lfs pull'
  ```

- **CANN开发分支代码获取**

  方式一（推荐）：通过repo + ssh下载（需注册公钥，请参考[GitCode帮助中心](https://docs.gitcode.com/docs/help/home/user_center/security_management/ssh)）。

  ```
  mkdir cann
  cd cann
  repo init -u git@gitcode.com:cann/manifest.git -b master --no-repo-verify -m cann-dev.xml
  repo sync -c --no-tags -j12
  ```

  方式二：通过repo + https下载。

  ```
  mkdir cann
  cd cann
  repo init -u https://gitcode.com/cann/manifest.git -b master --no-repo-verify -m cann-dev.xml
  repo sync -c --no-tags -j12
  ```

# 代码工程介绍

## 代码结构及仓库结构

| 组件 | 描述 | 源码仓 |
|------|------|--------|
| **算子库** | 提供了丰富的深度优化、硬件亲和的高性能算子，为神经网络在昇腾硬件上加速计算提供基础。 | ops-nn<br>ops-math<br>ops-transformer<br>ops-cv |
| **通信库** | 基于昇腾硬件的高性能通信库，提供单机多卡及多机多卡间的数据并行、模型并行通信方案。 | hixl<br>shmem<br>hccl<br>hcomm |
| **领域加速库** | 针对特定领域或场景的算子和算法的结合。 | ascend-transformer-boost<br>sip |
| **图引擎** | 面向昇腾的图编译器和执行器，提供图优化、多流并行、内存复用和模型下沉等功能。 | ge<br>metadef<br>graph-autofusion<br>triton-inference-server-ge-backend |
| **编程语言** | CANN针对算子开发场景推出的编程语言，最大化匹配用户开发习惯，提供算子模板库，支持算子极简编程。 | asc-devkit<br>pyasc<br>pypto<br>pto-isa<br>atvoss<br>catlass |
| **运行时** | 提供了高效的硬件资源管理、媒体数据预处理、单算子加载执行、模型推理等开发接口，供开发者轻松构建高性能人工智能应用。 | runtime |
| **驱动** | 提供了基础驱动、设备管理、资源管理及调度、通信能力等功能，使能昇腾芯片，充分发挥硬件能力，支撑CANN上层软件高效稳定运行。 | driver |
| **工具** | 提供CANN平台的各种工具，如故障定位、模型压缩等。 | oam-tools<br>amct |


具体请参考：[https://gitcode.com/cann](https://gitcode.com/cann)。
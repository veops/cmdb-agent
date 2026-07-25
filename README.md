<p align="center">
  <a href="https://veops.cn">
    <img src="images/logo.png" alt="VE Ops" width="300">
  </a>
</p>

<h1 align="center">OneAgent Community Edition</h1>

<p align="center">
  面向维易 CMDB 的跨平台资产采集与自动发现 Agent
</p>

<p align="center">
  <a href="https://github.com/veops/cmdb-agent/releases/latest"><img src="https://img.shields.io/github/v/release/veops/cmdb-agent?display_name=tag" alt="Latest release"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPL--3.0-brightgreen" alt="License: AGPL-3.0"></a>
  <a href="https://github.com/veops/cmdb"><img src="https://img.shields.io/badge/CMDB-veops%2Fcmdb-1677ff" alt="VE Ops CMDB"></a>
</p>

## 项目简介

OneAgent 是维易 CMDB 自动发现体系中的采集端，部署在需要纳管的主机上，负责执行资产采集与发现任务，并将结果发送给 OneMaster。本仓库用于发布 **OneAgent 社区版** 的跨平台二进制文件及相关资源。

> [!IMPORTANT]
> OneAgent 不能独立运行，必须连接 OneMaster 使用。请先参照[安装文档](https://veops.cn/docs/docs/cmdb/Agent/agent_install/)完成服务端部署，或通过[维易官网](https://veops.cn/user/login?redirect=%2Fapply)申请 OneMaster。

## 社区版能力

- 主机资产：物理机、虚拟机、PC、CPU、内存、网卡、磁盘等软硬件信息
- 网络设备：通过 SNMP 发现交换机、路由器、防火墙和打印机
- 公有云主机：阿里云 ECS、腾讯云 CVM、华为云 ECS、AWS EC2
- IPAM：子网存活探测及网络邻居信息采集
- 自定义发现：最多启用 3 个自定义 Python 发现插件
- 任务执行：支持配置同步、定时采集、日志记录和结果上报

企业版提供更完整的发现能力与规模支持，包括 VMware、云网络与 CDN、云存储、云数据库等资源类型。可通过[官网](https://veops.cn/#hero)联系我们。

## 下载

请从 [GitHub Releases](https://github.com/veops/cmdb-agent/releases) 下载与目标环境匹配的压缩包：

| 操作系统 | 架构 | Release 文件 |
| --- | --- | --- |
| Linux | amd64 | `oneagent-linux-amd64.tar.gz` |
| Linux | arm64 | `oneagent-linux-arm64.tar.gz` |
| Windows | amd64 | `oneagent-windows-amd64.tar.gz` |
| Windows | arm64 | `oneagent-windows-arm64.tar.gz` |
| macOS | amd64 | `oneagent-darwin-amd64.tar.gz` |
| macOS | arm64 | `oneagent-darwin-arm64.tar.gz` |

`discover-linux-amd64.tar.gz` 是 Linux 自动发现插件，不是 OneAgent 主程序。只有使用对应发现能力时才需要单独下载和部署。

### 校验文件

新版本同时提供 `checksums.txt`。下载后可校验文件完整性：

```bash
sha256sum -c checksums.txt
```

macOS 可使用：

```bash
shasum -a 256 -c checksums.txt
```

## 安装

以 Linux amd64 为例：

```bash
tar -xzf oneagent-linux-amd64.tar.gz
chmod +x oneagent
```

解压后请按照[安装指导](https://veops.cn/docs/docs/cmdb/Agent/agent_install/)将二进制文件放入部署目录，配置唯一的 Agent ID、Agent 名称以及 OneMaster 地址，再安装并启动服务。

常用服务命令：

```bash
./oneagent install -c /etc/oneagent.yaml
./oneagent start
./oneagent status
./oneagent stop
```

## 相关项目

- [维易 CMDB](https://github.com/veops/cmdb)
- [产品文档](https://veops.cn/docs/)
- [问题反馈](https://github.com/veops/cmdb-agent/issues)

## 许可证

本项目采用 [GNU Affero General Public License v3.0](LICENSE) 许可证。

## 社区交流

欢迎关注“维易科技 OneOps”公众号，获取产品动态并加入技术交流群。

<p align="center">
  <img src="images/wechat.png" alt="公众号：维易科技 OneOps" width="360">
</p>

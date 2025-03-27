# 使用Linux一键重装脚本为Raksmart VPS安装纯净版Debian系统指南

## 前言
对于Raksmart云服务器、VPS或独立服务器用户来说，安装自定义纯净版系统是常见的运维需求。本文将详细介绍如何使用Linux服务器一键重装系统脚本，在Raksmart VPS的CentOS 7.9环境中安装纯净版Debian 11系统。

👉 [【点击查看】2025年最新 Raksmart 优惠码及特价云服务器方案汇总](https://bit.ly/raksmart)

## 准备工作
1. **环境要求**：
   - Raksmart VPS（本文使用美国圣何塞节点）
   - 默认CentOS 7.9系统
   - SSH连接工具

2. **注意事项**：
   - 重装前务必备份重要数据
   - 确保网络连接稳定
   - 预留至少30分钟操作时间

## 详细操作步骤

### 1. 下载一键重装脚本
通过SSH连接VPS后，执行以下命令：

bash
yum -y install wget
wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/leitbogioro/Tools/master/Linux_reinstall/InstallNET.sh' && chmod a+x InstallNET.sh

### 2. 安装必要依赖
更新系统并安装必要组件：

bash
yum update --allowerasing -y
yum install wget -y

### 3. 执行系统重装
安装Debian 11纯净版系统（使用日本镜像源）：

bash
bash InstallNET.sh -debian 11 -mirror "http://ftp.riken.jp/Linux/debian/debian/"

> 注意：默认SSH端口为22，root密码为`LeitboGi0ro`，安装完成后请立即修改密码

### 4. 等待安装完成
安装过程约需30分钟，出现以下情况表示安装成功：
- 可以使用默认密码通过SSH重新连接
- 执行`lsb_release -a`命令显示Debian 11系统信息

## 常见问题处理
1. **安装失败**：通过Raksmart控制面板重新安装原系统
2. **连接超时**：检查VPS网络状态和防火墙设置
3. **镜像下载慢**：尝试更换其他地区的镜像源

## 系统验证
成功安装后，执行以下命令验证系统版本：

bash
lsb_release -a

## 结语
通过本教程，您可以轻松在Raksmart VPS上安装纯净版Linux系统。如需更多服务器管理技巧，欢迎持续关注我们的技术专栏。

[立即获取Raksmart最新优惠方案](https://bit.ly/raksmart)
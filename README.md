# BBR v3 Manager

一个功能强大的 BBR v3 内核管理和网络加速脚本，支持多种队列算法和自动安装功能。

## 🚀 功能特色

### 🔧 内核管理
- **自动安装 BBR v3 内核** - 从 GitHub Releases 自动下载最新内核
- **版本管理** - 支持安装指定版本或最新版本
- **智能引导更新** - 自动检测并更新 GRUB 或 U-Boot
- **内核卸载** - 安全卸载已安装的 BBR 内核

### ⚡ 网络加速
- **多种队列算法** - 支持 FQ、FQ_CODEL、FQ_PIE、CAKE
- **实时配置** - 立即应用网络配置
- **永久保存** - 可选择永久保存配置到系统
- **模块自动加载** - 配置开机自动加载内核模块

### 🔍 状态监控
- **BBR 状态检查** - 检测 BBR v3 是否已安装并生效
- **当前配置显示** - 显示当前的拥塞控制和队列算法
- **架构检测** - 自动检测系统架构并适配

## 🛠️ 系统要求

- **操作系统**: Debian/Ubuntu 系统
- **架构**: x86_64 或 aarch64 (ARM64)
- **依赖**: curl, wget, dpkg, awk, sed, sysctl, jq

## 🚀 使用方法

### 快速开始
```bash
# 下载并运行脚本
curl -sL https://raw.githubusercontent.com/qianyianyi/bbr-v3-manager/main/bbr-manager.sh | bash

# 或者克隆仓库后运行
git clone https://github.com/qianyianyi/bbr-v3-manager.git
cd bbr-v3-manager
chmod +x bbr-manager.sh
./bbr-manager.sh
```

## 📋 功能菜单

| 编号 | 功能 | 描述 |
|------|------|------|
| 1 | 🚀 安装或更新 BBR v3 | 安装最新版 BBR v3 内核 |
| 2 | 📚 指定版本安装 | 选择特定版本安装 |
| 3 | 🔍 检查 BBR v3 状态 | 检查 BBR v3 安装状态 |
| 4 | ⚡ 启用 BBR + FQ | 使用 FQ 队列算法 |
| 5 | ⚡ 启用 BBR + FQ_CODEL | 使用 FQ_CODEL 队列算法 |
| 6 | ⚡ 启用 BBR + FQ_PIE | 使用 FQ_PIE 队列算法 |
| 7 | ⚡ 启用 BBR + CAKE | 使用 CAKE 队列算法 |
| 8 | 🗑️ 卸载 BBR 内核 | 卸载已安装的 BBR 内核 |

## 🔧 队列算法说明

### FQ (Fair Queueing)
- **特点**: 公平队列，均衡流量分配
- **适用**: 通用场景，性能稳定

### FQ_CODEL
- **特点**: 结合 FQ 和 CoDel 算法
- **适用**: 减少缓冲膨胀，适合高延迟网络

### FQ_PIE 
- **特点**: 结合 FQ 和 PIE 算法
- **适用**: 主动队列管理，减少延迟

### CAKE
- **特点**: 综合队列管理算法
- **适用**: 复杂网络环境，智能流量控制

## ⚠️ 注意事项

1. **系统要求**: 仅支持 Debian/Ubuntu 系统
2. **架构限制**: 仅支持 x86_64 和 aarch64 架构
3. **权限要求**: 需要 root 权限进行内核安装
4. **重启要求**: 安装内核后需要重启系统
5. **数据备份**: 建议在操作前备份重要数据

## 🔍 验证安装

安装完成后，可以通过以下命令验证：

```bash
# 检查当前拥塞控制算法
sysctl net.ipv4.tcp_congestion_control

# 检查当前队列算法
sysctl net.core.default_qdisc

# 检查 BBR 模块版本
modinfo tcp_bbr | grep version
```

## 📝 作者信息

- **作者**: Joey
- **博客**: [https://joeyblog.net](https://joeyblog.net)
- **反馈群组**: [https://t.me/+ft-zI76oovgwNmRh](https://t.me/+ft-zI76oovgwNmRh)

## 📄 许可证

MIT License
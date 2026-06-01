# Stasis

[English](README.md) | **简体中文**

**为你的 MacBook 打造的更聪明的电池菜单栏图标。** 在菜单栏中即可监控电源指标、管理充电上限，并延长电池寿命。

Stasis 让你实时洞察 MacBook 的电源系统，并直接掌控充电行为，无需依赖 macOS 那套并不透明的「优化电池充电」。

> **仅支持 Apple Silicon。** 在不同平台上读取指标与控制充电所需的策略和底层机制差异很大。目前本应用仅支持搭载 Apple Silicon 的 MacBook。
>
> 需要 **macOS 14.8 及以上**。

![Stasis 菜单栏](https://github.com/srimanachanta/Stasis/wiki/images/FullApp.jpg)

## 安装

### Homebrew（推荐）

```bash
brew install --cask srimanachanta/tap/stasis
```
*如果遇到 macOS 的「已隔离」（quarantine）警告，请运行：*
```bash
xattr -dr com.apple.quarantine /Applications/Stasis.app
```

### 直接下载

1. 从 [GitHub Releases](https://github.com/srimanachanta/Stasis/releases) 下载。
2. 打开 `.zip` 文件，并将 Stasis 拖入 `/Applications`。
3. 移除隔离标记：
   ```bash
   xattr -cr /Applications/Stasis.app
   ```
4. 在「应用程序」中打开 Stasis。

## 主要功能

- **充电上限（Charge Limit）** —— 设定最高充电电量（50–100%），在硬件层面强制执行，即使在睡眠期间也有效。
- **航行模式（Sailing Mode）** —— 让电池在可配置的区间内浮动，避免频繁的细碎充电。
- **自动放电（Automatic Discharge）** —— 在保持接通电源的同时，将电量放电至你设定的目标值。
- **过热保护（Heat Protection）** —— 当电池温度过高时暂停充电。
- **电源仪表板（Power Dashboard）** —— 在菜单栏中实时显示电压、电流、功率、温度、健康度和充放电次数。
- **电源流向图（Power Flow Diagram）** —— 以桑基图（Sankey）可视化实时电源分配。
- **MagSafe LED 控制** —— 达到上限时显示绿色，充电过程中显示橙色。

## 文档

如需了解详细的功能说明、设置讲解、架构信息以及常见问题，请参阅 **[Stasis Wiki](https://github.com/srimanachanta/Stasis/wiki)**。

## 从源码构建

```bash
git clone https://github.com/srimanachanta/Stasis.git
cd Stasis
open stasis.xcodeproj
```

需要 macOS 15.7+ 以及支持 Swift 6+ 的 Xcode。依赖项会通过 Swift Package Manager 自动解析。

## 参与贡献

欢迎提交 PR。对于较大的改动，请先创建 issue 进行讨论。

## 致谢

- [SMCKit](https://github.com/srimanachanta/SMCKit) —— SMC 访问库
- [AsahiLinux](https://asahilinux.org/) —— SMC 键位逆向工程
- [Battery-Toolkit](https://github.com/mhaeuser/Battery-Toolkit) —— SMC 键位文档

## 许可证

[GPL-3.0](LICENSE)

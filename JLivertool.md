# JLiverTool (增强版)

[![GitHub release (latest by date)](https://img.shields.io/github/downloads/xinrea/jlivertool/total.svg)](https://github.com/Xinrea/JLiverTool/releases)

> [!IMPORTANT]
> **本项目的原始地址：[https://github.com/Xinrea/JLiverTool](https://github.com/Xinrea/JLiverTool)**
>
> 本仓库基于原项目进行功能增强，核心代码版权归原作者所有。如有任何问题，请优先访问原仓库获取官方版本。

> [!NOTE]
> 本项目自 3.0.0 版本开始，使用 Rust 重构，并使用 GPUI 框架；旧 Electron 版本请参考 [2.4.4](https://github.com/Xinrea/JLiverTool/releases/tag/2.4.4) 版本。

## 本仓库新增 / 增强功能

本增强版在原版 JLiverTool 基础上增加了以下实用功能：

### ✨ 鼠标穿透（可自定义快捷键，支持一键切换）

- 一键开启 / 关闭窗口鼠标穿透，窗口变得"透明可点击"，方便在直播时将工具窗口覆盖在 OBS 画面上而不遮挡操作
- **支持自定义全局快捷键**（默认 `Ctrl+Shift+P`），修改快捷键后旧快捷键自动失效，避免冲突
- 穿透状态下再按一次快捷键即可关闭，无需通过托盘菜单操作
- 同时支持系统托盘菜单中切换穿透状态

### 🎨 UI 色彩根据礼物 / SC 价值动态变化

- 礼物记录条目根据礼物价格高低显示不同的颜色深度，高价值礼物一眼识别
- 醒目留言（SuperChat / SC）根据金额等级自动应用对应的背景色和边框色，与 B 站官方视觉风格一致
- 视觉层次分明，高价值互动不再错过

### 🔍 主界面透明度可调

- 在设置中自由调整主界面窗口的透明度（0% ~ 100%）
- 适用于覆盖在直播画面 / OBS 场景上作为弹幕叠加层使用
- 支持独立的 Dashboard（合并视图）透明度设置

### 🪟 主界面一键开关独立窗口

- 顶部菜单栏按钮即可快速打开 / 关闭：
  - 🎁 礼物窗口
  - 💬 醒目留言（SC）窗口
  - 📊 统计数据窗口
  - 👥 观众列表 / 高能榜窗口
  - ⚙️ 设置窗口
- 各窗口独立置顶、独立调节透明度，无需额外操作

### 🅰️ 送礼用户用户名拼音 / 罗马音标注

- 在礼物、SC、舰长等互动记录中，自动为中文用户名标注**拼音（带声调）**，日文用户名标注**罗马音（Romaji）**
- 主播在念 ID 感谢时无需再查读音，提升直播流畅度
- 标注信息在 TTS 语音播报中同步支持

---

## 使用说明

### 1. 主界面（弹幕界面）

<table>
  <tr>
    <td>
      <img src="docs/public/mainwindow.png" alt="screenshot" width="500">
    </td>
    <td>
      <img src="docs/public/command.png" alt="screenshot" width="500">
    </td>
  </tr>
</table>

主界面分为三个大的部分：顶部菜单栏、弹幕列表、底部状态栏。
顶部菜单栏从左到右分别为：

- 置顶
- 礼物窗口
- 醒目留言窗口
- 统计窗口
- 观众列表窗口
- 设置窗口

底部状态栏显示当前的直播间标题，且提供了弹幕命令输入。输入普通内容后点击发送按钮即可发送弹幕。如果输入特殊命令，则会执行特殊功能。
目前支持的指令有：

- `/title <new title>` - 修改直播间标题
- `/bye` - 关闭直播

### 2. 礼物窗口

![giftwindow](docs/public/giftwindow.png)

礼物窗口用于单独显示礼物和舰长记录。

### 3. 醒目留言界面

![superchatwindow](docs/public/superchatwindow.png)

### 4. 设置界面

![设置窗口](docs/public/settings.png)

当登录账号与直播间号匹配时，直播间标题设置和开/关播按钮才可使用。

## 安装说明

### Windows

直接下载 Release 页面中的 `.exe` 安装包或便携版，双击运行即可。

### macOS

由于应用未经 Apple 签名，首次运行时可能提示"文件已损坏"。请在终端中执行以下命令：

```bash
xattr -cr /Applications/JLiverTool.app
```

### Arch Linux

下载 `PKGBUILD` 和 `jlivertool_*_x86_64.tar.gz` 到同一目录，然后执行：

```bash
makepkg -si
```

## 开发说明

### Run

```bash
cargo run
```

### Build

```bash
# Install cargo-packager
cargo install cargo-packager --locked

# Build release binary first
cargo build --release

# Create installers (run from project root)
cargo packager --release
```

## 致谢 & 原项目声明

再次感谢原作者 [Xinrea](https://github.com/Xinrea) 开发的 JLiverTool，本仓库仅做功能增强。

- **原项目仓库**：[https://github.com/Xinrea/JLiverTool](https://github.com/Xinrea/JLiverTool)
- **原项目文档站**：[https://xinrea.github.io/JLiverTool/](https://xinrea.github.io/JLiverTool/)
- 本仓库的发行版仅用于测试和交流，如需稳定版本请从原项目 Release 下载。

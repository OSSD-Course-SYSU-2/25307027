# 六子棋游戏 (Six Chess Game)

<div align="center">

![HarmonyOS](https://img.shields.io/badge/HarmonyOS-6.0.2(22)-blue.svg)
![ArkTS](https://img.shields.io/badge/ArkTS-1.0-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**一款基于 HarmonyOS 开发的六子棋单机小游戏**

[功能特性](#功能特性) • [快速开始](#快速开始) • [游戏规则](#游戏规则) • [技术架构](#技术架构) • [贡献指南](#贡献指南)

</div>

---

## 📖 项目简介

六子棋游戏是一款经典的策略棋类游戏，类似于五子棋，但需要连成六子才能获胜。本项目使用 HarmonyOS 原生开发框架 ArkTS 实现，提供了流畅的游戏体验和精美的用户界面。

### 🎮 游戏截图

<div align="center">
  <img src="docs/images/gameplay.png" alt="游戏界面" width="300"/>
  <p><em>游戏主界面</em></p>
</div>

---

## ✨ 功能特性

- **🎯 核心玩法**
  - 15×15 标准棋盘
  - 双人对战模式（黑棋先手）
  - 横、竖、斜任意方向连成六子获胜

- **🎨 精美界面**
  - 简洁现代的 UI 设计
  - 流畅的交互动画
  - 清晰的游戏状态提示

- **⚡ 游戏功能**
  - 实时显示当前玩家
  - 步数统计
  - 最后一步标记
  - 悔棋功能
  - 新游戏重置
  - 游戏结束提示

- **📱 平台支持**
  - 支持手机、平板、2合1设备
  - 自适应屏幕尺寸

---

## 🚀 快速开始

### 环境要求

- **DevEco Studio**: 4.0 或更高版本
- **HarmonyOS SDK**: 6.0.2(22) 或更高版本
- **Node.js**: 14.x 或更高版本

### 安装步骤

1. **克隆项目**
   ```bash
   git clone https://github.com/yourusername/SixChessGame.git
   cd SixChessGame
   ```

2. **打开项目**
   - 启动 DevEco Studio
   - 选择 `File` -> `Open`
   - 选择项目根目录

3. **配置项目**
   - 等待项目初始化完成
   - 如有依赖更新提示，点击 `Update`

4. **运行项目**
   - 连接 HarmonyOS 设备或启动模拟器
   - 点击运行按钮或按 `Shift + F10`

### 构建发布

```bash
# Debug 版本
hvigorw assembleHap --mode module -p product=default

# Release 版本
hvigorw assembleHap --mode module -p product=default -p buildMode=release
```

---

## 🎲 游戏规则

### 基本规则

1. **棋盘**: 15×15 的方格棋盘
2. **棋子**: 黑棋和白棋两种
3. **先手**: 黑棋先行
4. **轮流**: 双方轮流下棋
5. **获胜**: 任意方向（横、竖、斜）连成 6 个同色棋子获胜
6. **平局**: 棋盘填满且无人获胜则为平局

### 操作说明

- **下棋**: 点击棋盘空位放置棋子
- **悔棋**: 点击"悔棋"按钮撤销上一步
- **新游戏**: 点击"新游戏"按钮重新开始

---

## 🏗️ 技术架构

### 项目结构

```
SixChessGame/
├── AppScope/                    # 应用全局配置
│   ├── app.json5               # 应用配置文件
│   └── resources/              # 全局资源
│       └── base/
│           ├── element/        # 字符串、颜色等资源
│           └── media/          # 图片资源
├── entry/                       # 主模块
│   ├── src/
│   │   └── main/
│   │       ├── ets/            # ArkTS 源码
│   │       │   ├── entryability/  # 应用入口
│   │       │   ├── pages/         # 页面
│   │       │   │   └── Index.ets  # 主页面
│   │       │   └── common/        # 公共模块
│   │       │       └── SixChessGame.ets  # 游戏核心逻辑
│   │       └── resources/      # 模块资源
│   │           └── base/
│   │               ├── element/    # 字符串、颜色
│   │               ├── media/      # 图片
│   │               └── profile/    # 配置文件
│   ├── build-profile.json5     # 构建配置
│   ├── module.json5            # 模块配置
│   └── oh-package.json5        # 依赖配置
├── build-profile.json5         # 应用构建配置
├── oh-package.json5            # 项目依赖配置
└── hvigorfile.ts              # 构建脚本
```

### 核心技术

- **开发语言**: ArkTS (TypeScript 扩展)
- **UI 框架**: ArkUI 声明式开发范式
- **状态管理**: @State 装饰器
- **构建工具**: Hvigor

### 关键类说明

#### `SixChessGame` - 游戏核心类

```typescript
class SixChessGame {
  // 初始化游戏
  constructor()

  // 重置游戏
  reset(): void

  // 下棋
  makeMove(row: number, col: number): boolean

  // 悔棋
  undoMove(): boolean

  // 获取游戏状态
  getGameState(): GameState

  // 获取当前玩家
  getCurrentPlayer(): PieceType
}
```

#### 枚举类型

```typescript
// 棋子类型
enum PieceType {
  EMPTY = 0,  // 空
  BLACK = 1,  // 黑棋
  WHITE = 2   // 白棋
}

// 游戏状态
enum GameState {
  PLAYING = 0,     // 游戏中
  BLACK_WIN = 1,   // 黑棋胜
  WHITE_WIN = 2,   // 白棋胜
  DRAW = 3         // 平局
}
```

---

## 🤝 贡献指南

欢迎贡献代码、报告问题或提出建议！

### 如何贡献

1. **Fork 项目**
   ```bash
   git clone https://github.com/yourusername/SixChessGame.git
   ```

2. **创建分支**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **提交更改**
   ```bash
   git commit -m 'Add some feature'
   ```

4. **推送分支**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **创建 Pull Request**

### 代码规范

- 遵循 ArkTS 编码规范
- 保持代码简洁清晰
- 添加必要的注释
- 确保代码可编译运行

---

## 📝 开发计划

- [ ] 添加 AI 对战模式
- [ ] 支持多种棋盘大小
- [ ] 添加游戏历史记录
- [ ] 支持在线对战
- [ ] 添加音效和背景音乐
- [ ] 支持主题切换
- [ ] 添加游戏教程

---

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE) 开源协议。

---

## 🙏 致谢

- 感谢华为 HarmonyOS 团队提供的优秀开发框架
- 感谢所有贡献者的支持

---

## 📮 联系方式

- **问题反馈**: [GitHub Issues](https://github.com/yourusername/SixChessGame/issues)
- **功能建议**: [GitHub Discussions](https://github.com/yourusername/SixChessGame/discussions)

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给一个 Star ⭐**

Made with ❤️ by HarmonyOS Developer

</div>

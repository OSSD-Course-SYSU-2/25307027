# 🐍 贪吃蛇游戏 - HarmonyOS版

[![HarmonyOS](https://img.shields.io/badge/HarmonyOS-6.0.2(22)-blue.svg)](https://www.harmonyos.com/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-orange.svg)](https://github.com)

一个基于鸿蒙(HarmonyOS) ArkTS开发的经典贪吃蛇小游戏，具有精美的UI界面和流畅的游戏体验。

## ✨ 功能特性

- 🎮 **经典玩法** - 传统的贪吃蛇游戏机制
- 🎨 **精美UI** - 现代化的深色主题设计
- 📱 **触控支持** - 方向按钮控制，操作简单
- ⏸️ **暂停功能** - 随时暂停和继续游戏
- 🏆 **分数系统** - 实时分数显示和最高分记录
- 🔄 **重新开始** - 游戏结束后可快速重新开始

## 📸 游戏截图

<div align="center">
  <img src="screenshots/gameplay.png" alt="游戏界面" width="300"/>
  <p>游戏主界面</p>
</div>

## 🎯 游戏规则

1. 使用方向按钮控制蛇的移动方向
2. 吃到红色食物可以增加蛇的长度和分数
3. 撞到墙壁或自己的身体游戏结束
4. 尽可能获得更高的分数！

## 🛠️ 技术栈

- **开发框架**: HarmonyOS Next
- **开发语言**: ArkTS (TypeScript扩展)
- **UI框架**: ArkUI 声明式UI
- **目标SDK**: HarmonyOS 6.0.2(22)

## 📦 项目结构

```
test/
├── AppScope/              # 应用全局配置
│   ├── app.json5         # 应用配置文件
│   └── resources/        # 全局资源文件
├── entry/                # 主模块
│   └── src/
│       └── main/
│           ├── ets/      # ArkTS源代码
│           │   ├── model/
│           │   │   └── SnakeGame.ets    # 游戏逻辑模型
│           │   └── pages/
│           │       └── Index.ets        # 游戏主页面
│           ├── resources/               # 资源文件
│           └── module.json5             # 模块配置
├── build-profile.json5   # 构建配置
├── hvigorfile.ts         # 构建脚本
└── README.md             # 项目说明文档
```

## 🚀 快速开始

### 前置要求

- DevEco Studio 5.0 或更高版本
- HarmonyOS SDK 6.0.2(22) 或更高版本
- Node.js 14.x 或更高版本

### 安装步骤

1. **克隆项目**
   ```bash
   git clone https://github.com/yourusername/harmonyos-snake-game.git
   cd harmonyos-snake-game
   ```

2. **打开项目**
   - 启动 DevEco Studio
   - 选择 `File -> Open`
   - 选择项目根目录

3. **配置项目**
   - 等待项目初始化和依赖下载完成
   - 配置签名证书（如需真机调试）

4. **运行项目**
   - 连接HarmonyOS设备或启动模拟器
   - 点击运行按钮或按 `Shift + F10`

## 🎮 操作说明

| 操作 | 说明 |
|------|------|
| ▲ | 向上移动 |
| ▼ | 向下移动 |
| ◀ | 向左移动 |
| ▶ | 向右移动 |
| ⏸ | 暂停游戏 |
| ▶ | 继续游戏 |

## 🔧 核心实现

### 游戏模型 (SnakeGame.ets)

游戏核心逻辑包括：
- 蛇的移动和生长机制
- 食物随机生成算法
- 碰撞检测（墙壁和自身）
- 方向控制和防反向移动
- 分数和游戏状态管理

### UI界面 (Index.ets)

界面实现特点：
- 使用 `@State` 装饰器实现响应式UI更新
- `ForEach` 循环渲染游戏网格
- `setInterval` 实现游戏循环
- 自定义 `@Builder` 组件化构建UI

## 🎨 自定义配置

### 修改游戏速度

在 `Index.ets` 中修改 `gameSpeed` 参数：

```typescript
private gameSpeed: number = 150; // 毫秒，数值越小速度越快
```

### 修改游戏区域大小

在 `SnakeGame.ets` 中修改网格参数：

```typescript
private gridWidth: number = 20;  // 网格宽度
private gridHeight: number = 30; // 网格高度
```

### 修改颜色主题

在 `Index.ets` 的样式中修改颜色值：

```typescript
.backgroundColor('#1a1a2e')  // 背景色
.backgroundColor('#e94560')  // 强调色
.backgroundColor('#32cd32')  // 蛇身颜色
```

## 📝 开发日志

### v1.0.0 (2024-04-14)
- ✅ 实现基础游戏功能
- ✅ 完成UI界面设计
- ✅ 添加暂停和重新开始功能
- ✅ 实现分数系统

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

## 🙏 致谢

- 感谢华为 HarmonyOS 团队提供的优秀开发框架
- 感谢所有贡献者的支持

## 📧 联系方式

如有问题或建议，欢迎通过以下方式联系：

- 提交 [Issue](https://github.com/yourusername/harmonyos-snake-game/issues)
- 发送邮件至 your.email@example.com

---

<div align="center">
  <p>⭐ 如果这个项目对你有帮助，请给一个 Star ⭐</p>
  <p>Made with ❤️ for HarmonyOS</p>
</div>

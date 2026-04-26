# 贡献指南 (Contributing Guide)

感谢您考虑为六子棋游戏项目做出贡献！本文档将帮助您了解如何参与项目开发。

---

## 📋 目录

- [行为准则](#行为准则)
- [如何贡献](#如何贡献)
- [开发流程](#开发流程)
- [代码规范](#代码规范)
- [提交规范](#提交规范)
- [问题反馈](#问题反馈)

---

## 行为准则

### 我们的承诺

为了营造一个开放和友好的环境，我们承诺：

- 使用包容性的语言
- 尊重不同的观点和经验
- 优雅地接受建设性批评
- 关注对社区最有利的事情
- 对其他社区成员表示同理心

---

## 如何贡献

### 报告 Bug

如果您发现了 Bug，请：

1. 检查 [Issues](https://github.com/yourusername/SixChessGame/issues) 中是否已有相同问题
2. 如果没有，创建新的 Issue，包含：
   - 清晰的标题和描述
   - 复现步骤
   - 期望行为
   - 实际行为
   - 截图（如果适用）
   - 环境信息（设备型号、系统版本等）

### 提出新功能

如果您有新功能的想法：

1. 在 [Discussions](https://github.com/yourusername/SixChessGame/discussions) 中讨论
2. 说明功能的使用场景和价值
3. 等待社区反馈和确认

### 提交代码

1. **Fork 项目**
   ```bash
   git clone https://github.com/yourusername/SixChessGame.git
   cd SixChessGame
   ```

2. **创建分支**
   ```bash
   # 功能分支
   git checkout -b feature/amazing-feature

   # 修复分支
   git checkout -b fix/bug-description
   ```

3. **进行开发**
   - 遵循代码规范
   - 编写清晰的注释
   - 确保代码可编译运行

4. **提交更改**
   ```bash
   git add .
   git commit -m 'feat: add amazing feature'
   ```

5. **推送分支**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **创建 Pull Request**
   - 填写清晰的 PR 标题和描述
   - 关联相关的 Issue
   - 等待代码审查

---

## 开发流程

### 环境准备

1. 安装 DevEco Studio 4.0+
2. 配置 HarmonyOS SDK 6.0.2(22)+
3. 安装 Node.js 14.x+

### 开发步骤

1. **拉取最新代码**
   ```bash
   git pull origin main
   ```

2. **创建功能分支**
   ```bash
   git checkout -b feature/your-feature
   ```

3. **编写代码**
   - 在 `entry/src/main/ets/` 下开发
   - 遵循项目结构规范

4. **本地测试**
   - 在模拟器或真机上测试
   - 确保所有功能正常

5. **提交代码**
   - 遵循提交规范
   - 编写清晰的提交信息

---

## 代码规范

### ArkTS 编码规范

#### 命名规范

```typescript
// 类名：大驼峰
class SixChessGame { }

// 函数名：小驼峰
function calculateScore() { }

// 变量名：小驼峰
let currentPlayer: PieceType;

// 常量：全大写下划线
const BOARD_SIZE: number = 15;

// 枚举：大驼峰
enum GameState { }
```

#### 文件结构

```typescript
// 1. 导入语句
import { Module } from 'module';

// 2. 常量定义
const CONSTANT: string = 'value';

// 3. 类型定义
interface Config { }

// 4. 类定义
export class MyClass { }
```

#### 注释规范

```typescript
/**
 * 函数说明
 * @param param1 参数1说明
 * @param param2 参数2说明
 * @returns 返回值说明
 */
function myFunction(param1: string, param2: number): boolean {
  // 单行注释
  return true;
}
```

### UI 组件规范

```typescript
@Component
struct MyComponent {
  // 1. 状态变量
  @State private count: number = 0;

  // 2. 私有变量
  private data: string = '';

  // 3. 生命周期方法
  aboutToAppear() {
    // 初始化
  }

  // 4. 构建方法
  build() {
    Column() {
      // UI 构建
    }
  }

  // 5. 私有方法
  private handleClick() {
    // 处理逻辑
  }
}
```

---

## 提交规范

遵循 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/) 规范：

### 提交格式

```
<type>(<scope>): <subject>

<body>

<footer>
```

### 类型 (type)

- `feat`: 新功能
- `fix`: 修复 Bug
- `docs`: 文档更新
- `style`: 代码格式（不影响代码运行）
- `refactor`: 重构（既不是新增功能，也不是修复 Bug）
- `perf`: 性能优化
- `test`: 测试相关
- `chore`: 构建过程或辅助工具的变动
- `revert`: 回退

### 示例

```bash
# 新功能
git commit -m 'feat: add AI opponent mode'

# 修复 Bug
git commit -m 'fix: correct win detection algorithm'

# 文档更新
git commit -m 'docs: update README with new features'

# 重构
git commit -m 'refactor: optimize game logic performance'
```

---

## 问题反馈

### 反馈渠道

- **Bug 报告**: [GitHub Issues](https://github.com/yourusername/SixChessGame/issues)
- **功能建议**: [GitHub Discussions](https://github.com/yourusername/SixChessGame/discussions)
- **安全问题**: 请发送邮件至 security@example.com

### Issue 模板

```markdown
## 问题描述
[清晰简洁地描述问题]

## 复现步骤
1. 步骤一
2. 步骤二
3. ...

## 期望行为
[描述应该发生什么]

## 实际行为
[描述实际发生了什么]

## 环境信息
- 设备型号：
- 系统版本：
- 应用版本：

## 截图
[如果适用，添加截图]
```

---

## 🙏 感谢

感谢您的贡献！每一个贡献都让这个项目变得更好。

---

<div align="center">

**Happy Coding! 🎉**

</div>

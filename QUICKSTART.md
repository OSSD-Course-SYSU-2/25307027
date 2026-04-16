# 🚀 快速开始指南

## 5分钟上手贪吃蛇游戏

### 📋 前置检查

在开始之前，请确保您已安装：

- ✅ DevEco Studio 5.0+
- ✅ HarmonyOS SDK 6.0.2(22)+
- ✅ Node.js 14.x+

### ⚡ 快速运行

#### 方法一：使用 DevEco Studio

1. **打开项目**
   ```
   File → Open → 选择项目目录
   ```

2. **等待初始化**
   - 项目加载完成
   - 依赖自动下载

3. **运行应用**
   - 连接设备或启动模拟器
   - 点击 ▶️ 运行按钮
   - 或按 `Shift + F10`

#### 方法二：命令行运行

```bash
# 1. 进入项目目录
cd harmonyos-snake-game

# 2. 安装依赖（如果需要）
ohpm install

# 3. 构建项目
hvigorw assembleHap

# 4. 安装到设备
hdc install entry-default-signed.hap
```

### 🎮 开始游戏

应用启动后，您将看到：

1. **游戏界面**
   - 蛇从左侧开始移动
   - 红色食物随机出现

2. **控制方式**
   - 点击方向按钮控制蛇
   - 点击 ⏸ 暂停游戏
   - 点击重新开始按钮重置

3. **游戏目标**
   - 吃到红色食物
   - 避免撞墙和撞自己
   - 获得更高分数！

### 🔧 常见问题

#### Q: 项目无法编译？
```
A: 检查 SDK 版本是否正确
   File → Settings → SDK → 确认版本
```

#### Q: 无法连接设备？
```
A: 1. 确认设备已开启开发者模式
   2. 确认 USB 调试已开启
   3. 运行 hdc list targets 检查连接
```

#### Q: 模拟器启动失败？
```
A: 1. 检查电脑虚拟化设置
   2. 在 BIOS 中开启 VT-x
   3. 重新创建模拟器
```

### 📱 测试设备

推荐测试设备：
- Huawei Mate 60 Pro
- Huawei P60 Pro
- HarmonyOS 模拟器

### 🎯 下一步

- 📖 阅读 [README.md](README.md) 了解详情
- 🏗️ 查看 [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md) 了解架构
- 🎮 参考 [DEMO.md](DEMO.md) 了解游戏机制
- 🤝 阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 参与贡献

### 💡 开发提示

#### 修改游戏速度
```typescript
// 在 Index.ets 中
private gameSpeed: number = 150; // 改为 100 更快，200 更慢
```

#### 修改网格大小
```typescript
// 在 SnakeGame.ets 中
private gridWidth: number = 20;  // 宽度
private gridHeight: number = 30; // 高度
```

#### 修改颜色主题
```typescript
// 在 Index.ets 中搜索颜色值
.backgroundColor('#1a1a2e')  // 修改背景色
```

### 🐛 调试技巧

1. **查看日志**
   ```
   DevEco Studio → Log → HiLog
   ```

2. **断点调试**
   - 在代码行号处点击设置断点
   - 点击 Debug 按钮
   - 查看变量值

3. **性能分析**
   ```
   Run → Profile 'entry'
   ```

### 📦 构建发布

#### 构建 HAP 包
```bash
# Debug 版本
hvigorw assembleHap --mode module -p product=default

# Release 版本
hvigorw assembleHap --mode module -p product=default -p buildMode=release
```

#### 签名配置
1. 生成签名证书
2. 配置签名信息
3. 构建签名包

### 🎉 开始探索

现在您已经准备好了！开始探索这个贪吃蛇游戏项目吧！

如果遇到问题，欢迎：
- 📝 提交 Issue
- 💬 查看文档
- 🤝 参与讨论

祝您开发愉快！🚀

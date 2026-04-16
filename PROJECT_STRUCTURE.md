# 项目结构说明

## 📁 目录结构

```
harmonyos-snake-game/
│
├── 📂 AppScope/                    # 应用全局配置目录
│   ├── 📄 app.json5               # 应用全局配置（包名、版本等）
│   └── 📂 resources/              # 全局资源
│       └── 📂 base/
│           └── 📂 element/
│               └── 📄 string.json # 应用名称等字符串资源
│
├── 📂 entry/                       # 主模块（入口模块）
│   └── 📂 src/
│       └── 📂 main/
│           ├── 📂 ets/             # ArkTS 源代码目录
│           │   ├── 📂 model/       # 数据模型层
│           │   │   └── 📄 SnakeGame.ets    # 游戏核心逻辑
│           │   │
│           │   ├── 📂 pages/       # 页面层
│           │   │   └── 📄 Index.ets        # 游戏主页面
│           │   │
│           │   ├── 📂 entryability/        # 应用入口能力
│           │   └── 📂 entrybackupability/  # 备份能力
│           │
│           ├── 📂 resources/       # 资源文件目录
│           │   ├── 📂 base/
│           │   │   ├── 📂 element/    # 字符串、颜色等
│           │   │   ├── 📂 media/      # 图片资源
│           │   │   └── 📂 profile/    # 配置文件
│           │   └── 📂 rawfile/        # 原始文件
│           │
│           └── 📄 module.json5     # 模块配置文件
│
├── 📂 oh_modules/                  # OpenHarmony 依赖包
│
├── 📂 .hvigor/                     # Hvigor 构建缓存
├── 📂 .idea/                       # IDE 配置
│
├── 📄 build-profile.json5          # 构建配置文件
├── 📄 hvigorfile.ts                # Hvigor 构建脚本
├── 📄 oh-package.json5             # 项目依赖配置
├── 📄 oh-package-lock.json5        # 依赖锁定文件
├── 📄 code-linter.json5            # 代码检查配置
├── 📄 local.properties             # 本地配置（SDK路径等）
│
├── 📄 README.md                    # 项目说明文档
├── 📄 LICENSE                      # 许可证文件
├── 📄 CONTRIBUTING.md              # 贡献指南
└── 📄 .gitignore                   # Git 忽略配置
```

## 🔑 核心文件说明

### 1. 应用配置文件

#### `AppScope/app.json5`
```json5
{
  "app": {
    "bundleName": "com.example.snakegame",  // 应用包名
    "vendor": "SnakeGame",                   // 开发者名称
    "versionCode": 1000000,                  // 版本号
    "versionName": "1.0.0",                  // 版本名称
    "icon": "$media:layered_image",          // 应用图标
    "label": "$string:app_name"              // 应用名称
  }
}
```

#### `entry/src/main/module.json5`
定义模块的基本信息、能力（Ability）配置等。

### 2. 游戏核心代码

#### `entry/src/main/ets/model/SnakeGame.ets`
游戏逻辑模型，包含：
- 游戏状态管理
- 蛇的移动算法
- 碰撞检测
- 食物生成
- 分数计算

#### `entry/src/main/ets/pages/Index.ets`
游戏主界面，包含：
- UI 渲染逻辑
- 游戏循环控制
- 用户交互处理
- 界面布局设计

### 3. 构建配置

#### `build-profile.json5`
定义构建参数、SDK版本、模块配置等。

#### `hvigorfile.ts`
Hvigor 构建系统的配置脚本。

## 🎮 游戏架构

### MVC 架构模式

```
┌─────────────────────────────────────┐
│           View (UI Layer)            │
│         Index.ets                    │
│  - 游戏界面渲染                       │
│  - 用户交互处理                       │
│  - 状态显示                          │
└──────────────┬──────────────────────┘
               │
               │ 数据绑定
               │
┌──────────────▼──────────────────────┐
│         Model (Data Layer)           │
│        SnakeGame.ets                 │
│  - 游戏状态                          │
│  - 业务逻辑                          │
│  - 数据计算                          │
└─────────────────────────────────────┘
```

### 数据流

```
用户操作 → Index.ets → SnakeGame.ets → 更新状态 → UI 刷新
    ↓
方向按钮 → changeDirection() → 更新方向 → moveSnake()
    ↓
暂停按钮 → togglePause() → 更新状态 → UI 响应
    ↓
重新开始 → restart() → 重置游戏 → 重新渲染
```

## 🔧 扩展建议

### 添加新功能

1. **音效支持**
   - 在 `resources/rawfile/` 添加音频文件
   - 使用 AVPlayer API 播放音效

2. **难度选择**
   - 在 SnakeGame 中添加难度参数
   - 根据难度调整游戏速度

3. **排行榜**
   - 使用 Preferences API 存储分数
   - 创建新的页面显示排行榜

4. **主题切换**
   - 定义多套颜色主题
   - 使用 @StorageLink 实现主题切换

### 性能优化

- 使用 Canvas 替代网格渲染（大量单元格时）
- 优化状态更新频率
- 使用 LazyForEach 懒加载

## 📚 相关文档

- [HarmonyOS 开发文档](https://developer.harmonyos.com/cn/docs/)
- [ArkTS 语法参考](https://developer.harmonyos.com/cn/docs/documentation/doc-guides-V3/arkts-getting-started-0000001504769321-V3)
- [ArkUI 组件参考](https://developer.harmonyos.com/cn/docs/documentation/doc-references-V3/ts-components-summary-0000001544703781-V3)

# 多功能计算器（Vela 快应用）

一款运行于小米手环 pro系列（Vela 快应用）的科学计算器。支持基础四则运算、科学函数、位运算，并提供可开关的二进制/十六进制结果对照。

> 包名：`com.moumou2910.bandcalc`
> 目标设备：小米手环 Pro系列（矩形屏 336×480）

---

## ✨ 功能特性

- **基础运算**：加 `+`、减 `−`、乘 `×`、除 `÷`、小数、正负号 `±`、百分号 `%`、退格 `DEL`、清空 `AC`
- **科学函数**：`sin / cos / tan`（角度制）、`log / ln`、开根号 `√`、平方 `x²`、幂 `x^y`
- **位运算**：按位与 `&`、或 `|`、异或 `⊕`、取反 `~`、左移 `<<`、右移 `>>`
- **常用常数**：圆周率 `π`、自然常数 `e`
- **结果对照**：结果显示区下方自动展示二进制 / 十六进制（可通过设置页开关）
- **双页键盘**：标准页、科学 + 位运算页，左右滑动切换，底部有指示点
- **设置页**：支持开关进制对照显示，并自动记忆偏好（本地存储）

---

## 🛠 技术栈

- **框架**：Xiaomi Vela JS 快应用（基于 NuttX）
- **界面**：HTML + CSS + JavaScript，`.ux` 单文件（`template` / `script` / `style` 三段）
- **配置**：`manifest.json`
- **开发工具**：AIoT IDE（基于 VS Code）
- **打包**：`aiot build` / `aiot release`（经 npm 脚本）

---

## 📁 项目结构

```
多功能计算器/
├── dist/                        # 打包产物（.rpk）
│   └── com.moumou2910.bandcalc.release.1.0.0.rpk
├── src/
│   ├── app.ux                   # 应用入口（读取设备屏幕形状）
│   ├── manifest.json            # 应用配置（包名、路由、feature）
│   ├── config.back.json         # 后向兼容配置（bundleName）
│   ├── pages/
│   │   ├── index/index.ux       # 计算器主页（swiper 两页键盘 + 计算引擎）
│   │   └── settings/settings.ux # 设置页（进制对照开关）
│   └── resources/base/media/logo.png  # 应用图标（192×192）
├── package.json                 # npm 脚本（build / release / lint）
└── README.md
```

---

## ✅ 环境准备

1. 安装 **AIoT IDE**（Vela 快应用官方 IDE，基于 VS Code）。
2. 安装 **Node.js**、**JDK**、**Platform Tools（adb）**、**OpenSSL**。
3. 在 AIoT IDE 中创建/打开本工程，首次需「安装项目依赖」并「初始化模拟器环境」。

> 若 npm 报错（如 `npm.ps1 无法加载`），以管理员运行 PowerShell 执行：
> `set-ExecutionPolicy RemoteSigned`

---

## ▶️ 运行 / 调试

1. 用 AIoT IDE 打开工程。
2. 顶部「选择设备」选一个**矩形屏**设备（推荐「手环 9 Pro」，分辨率与手环 10 Pro 相同 336×480）。
3. 点击「调试」，在模拟器中左右滑动切换键盘。

### 测试示例

| 输入 | 结果 |
| --- | --- |
| `7 + 8 =` | 15 |
| `2 ^ 3 =` | 8 |
| `√ 9 =` | 3 |
| `3 0 sin` | 0.5 |
| `5 & 3 =` | 1 |
| `1 << 4 =` | 16 |

---

## 📦 打包

```bash
npm run build     # debug 包
npm run release   # release 包（正式签名）
```

产物输出到 `dist/`：

- `com.moumou2910.bandcalc.debug.1.0.0.rpk`
- `com.moumou2910.bandcalc.release.1.0.0.rpk`

---


## ⚠️ 注意事项

- **包名**：`com.moumou2910.bandcalc` 一旦发布/大量设备安装后**不要再改**，否则会被视为全新应用。
- **图标**：替换 `src/resources/base/media/logo.png`（推荐 192×192 PNG），改后需重新打包。
- **科学函数角度制**：`sin/cos/tan` 按角度计算，`sin 30 = 0.5`。

---

## 📝 后续可扩展

- 按键震动反馈
- 计算历史记录
- 结果保留小数位数设置
- 十进制 / 二进制 / 十六进制输入切换

# 本项目由AI编写
# 本README由AI编写

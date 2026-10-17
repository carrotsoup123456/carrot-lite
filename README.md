# carrot-lite + OC 摆渡·carrot 版 —— 安装说明

两个东西，按顺序装：

1. **carrot-lite**：主程序，你的 AI agent 桌面端。
2. **OC 摆渡·carrot 版**：配件，把 OpenCode 的免费模型一键导入 carrot。

---

## 第一步：装 carrot-lite

### Mac
- Apple 芯片（M1/M2/M3/M4）：`carrot-lite-1.0.0-mac-arm64.dmg`
- Intel 芯片：`carrot-lite-1.0.0-mac-x64.dmg`

打开 dmg，把 carrot-lite 拖进「应用程序」。
**第一次启动**：因为没付费签名，直接双击会被拦。到「应用程序」里**右键 carrot-lite → 打开**，弹窗里再点「打开」即可（只需这一次）。

### Windows
`carrot-lite-1.0.0-win-x64-setup.exe`，双击安装。
出现「Windows 已保护你的电脑」时，点「更多信息」→「仍要运行」。

启动后界面右下角有「API 库」。想用自己 Key 的话（DeepSeek 等）可以直接加；想用免费模型就继续第二步。

**装好第一次启动就有**：提示词工程师子 agent（prompt-engineer，帮你把大白话写成好提示词）+ 27 个精选技能全部默认启用——不想要的在技能面板里自己关掉就行，你的选择重启后会保持。

## 第二步：装 OC 摆渡·carrot 版（免费模型配件）

> 这个配件改装自开源项目 [RuiC-oc-ferry](https://github.com/HRuiCcc/RuiC-oc-ferry)（OC 摆渡，作者 HRuiCcc），感谢原作者。

### Mac
- Apple 芯片：`oc-ferry-carrot-1.0.0-mac-arm64.dmg`
- Intel 芯片：`oc-ferry-carrot-1.0.0-mac-x64.dmg`

同样拖进「应用程序」，第一次也要**右键 → 打开**。

### Windows
`oc-ferry-carrot-1.0.0-win-x64-setup.exe`，双击安装（SmartScreen 同样选「仍要运行」）。

### 用法
1. 先开着 carrot，再启动「OC 摆渡·carrot 版」。
2. 它第一次启动要下载模型服务并逐个检测模型，**等几分钟**，完事后会**自动导入** carrot。
3. 回到 carrot → 右下角「API 库」，能看到「**OpenCode 免费（OC 摆渡）**」，里面的模型直接选用即可。
4. 以后模型列表有更新，点配件面板里的「导入 carrot」刷新一次。

**注意：想用免费模型时，OC 摆渡要保持运行**（它是个本地代理，在托盘里挂着就行，不占什么事）。它退出时会自动把免费模型从 carrot 的 API 库里摘掉，避免 carrot 调到一个没在跑的服务。

## 常见问题

| 问题 | 怎么办 |
|---|---|
| 配件面板显示「连不上 carrot」 | 先启动 carrot，再点配件里的「导入 carrot」 |
| 免费模型突然从 API 库消失 | OC 摆渡被关了。重新打开它，等它自动导入 |
| 某个模型用不了 | 免费模型是 OpenCode 提供的，个别模型会临时不可用；在配件面板「检测全部模型」后再导入一次，换一个模型用 |
| 想用自己的 DeepSeek Key | carrot → API 库 → 添加服务商，接口地址 `https://api.deepseek.com/anthropic` |

## 数据放哪（想卸载干净的话）

| | carrot-lite | OC 摆渡·carrot 版 |
|---|---|---|
| Mac | `~/Library/Application Support/carrot-lite` | `~/Library/Application Support/oc-ferry-carrot` |
| Windows | `%APPDATA%\carrot-lite` | `%APPDATA%\oc-ferry-carrot` |

卸载 = 删 App + 删上面两个文件夹。

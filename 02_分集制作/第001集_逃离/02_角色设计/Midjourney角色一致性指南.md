# Midjourney 角色一致性 (Character Consistency) 操作指南

你已经有了完美的主角参考图（`主角.png`），为了在生成后续视频素材时保持角色外形的高度一致（固定脸型、发型、服装），我们需要使用 Midjourney 的 **Character Reference (`--cref`)** 功能。

## 1. 核心操作步骤

### 第一步：获取图片 URL
Midjourney 无法直接读取本地图片，必须使用在线链接。
1.  将 `主角.png` 发送到 Midjourney 的 Discord 频道（或者你私人的 Bot 对话框）。
2.  发送成功后，点击图片放大，右键选择 **"Copy Link" (复制链接)**。
    *   链接通常以 `https://cdn.discordapp.com/attachments/...` 或 `https://media.discordapp.net/...` 开头。

### 第二步：使用 `--cref` 参数
在生成新图时，在 Prompt 末尾加上 `--cref` 参数，后面跟上刚才复制的链接。

**语法格式：**
```
/imagine prompt: [你的描述词] --cref [图片链接] --cw [权重数值]
```

### 第三步：调整相似度权重 (`--cw`)
`--cw` (Character Weight) 控制参考的强弱，范围是 0 到 100。

*   **`--cw 100` (默认)**：**全套拷贝**。参考脸部、发型**以及衣服**。
    *   *适用场景*：角色在不同场景中穿着同一套衣服（例如：主角一直穿着那套改造成工装的旧西装）。
*   **`--cw 0`**：**只换脸**。重点参考脸部特征，但**忽略衣服和发型**。
    *   *适用场景*：如果你想给主角换衣服，或者让他改变发型。

---

## 2. 针对本项目的实操示例

假设你的主角图片链接是：`https://example.com/hero.png`

### 场景 A：主角在地铁上看手机（保持全套造型）
我们希望他穿的和参考图一模一样。

```
POV shot, futuristic subway commuters, protagonist looking at screen, mental wear interface --ar 16:9 --cref https://example.com/hero.png --cw 100
```

### 场景 B：主角在天台脱掉西装（需要换动作/衣服）
这里可能需要更多的动作自由度。

```
cinematic shot, protagonist standing on rooftop, taking off jacket, back view --ar 16:9 --cref https://example.com/hero.png --cw 100
```

---

## 3. 进阶技巧：如何微调

如果发现生成的脸不像，或者衣服不对：

1.  **确保参考图清晰**：你提供的 `主角.png` 是全身/半身照，最好再准备一张**清晰的大头照**（只包含脸部），专门用于需要特写表情的场景。
2.  **混合参考**：你可以同时使用多张参考图。
    `--cref URL1 URL2`
3.  **风格参考 (`--sref`)**：
    `--cref` 负责固定**角色**。
    `--sref` 负责固定**画风**（比如赛博朋克风）。
    **这两个参数可以同时使用！**

**终极公式：**
> `[Prompt] --ar 16:9 --cref [主角URL] --cw 100 --sref [画风URL]`

---

## 4. 你的任务清单

1.  [ ] 把 `主角.png` 上传到 Discord。
2.  [ ] 复制链接。
3.  [ ] 在使用《第1集剧本.md》中的 Prompt 时，将 `[Character_URL]` 替换为你复制的链接。

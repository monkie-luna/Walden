# Midjourney 视觉定调实操指南 (Visual Style Guide)

本指南旨在帮助你利用 Midjourney 快速锁定**“赛博瓦尔登守夜人”**的最终画风与主角形象。

---

## 第一步：锁定“赛博自然主义”画风 (The Style)

根据我们最新确定的“守夜人”人设（冰冷代码 vs 温暖自然），我们不再使用普通的风景照，而是要追求一种**“高智感”的冲突美学**。

**推荐方向：** 8K 电影级写实自然 + 微妙的数字干扰 (Glitch) / 悬浮 UI。

### 1. 测试画风 (Style Test)
请复制以下 4 条 Prompt 到 Midjourney (Discord) 中运行，选出最让你心动的一张图：

#### 方案 A：极致写实 + 赛博点缀 (推荐，最符合“守夜人”设定)
> **Prompt:**
> `cinematic shot of a cozy wooden cabin in a deep forest by a lake, night time, bioluminescent digital plants, subtle holographic data stream floating in the air, hyper realistic, 8k, tyndall effect, moody lighting, national geographic style mixed with cyberpunk aesthetic --ar 16:9 --style raw`

### 2. 固定画风 (Locking the Style via `--sref`)
当你生成了一张**完美**的图片（假设它是图 1）：
1.  右键点击该图 -> **Copy Link** (复制图片链接)。
2.  在接下来的所有 Prompt 后面加上：`--sref <图片链接> --sw 100`。
    *   *注：`--sref` (Style Reference) 会让 MJ 强行模仿这张图的色调、光影和笔触。*

---

## 第二步：设计主角“守夜人” (The Protagonist)

我们需要一个既像程序员又像隐士的角色。

### 1. 生成角色设定图 (Character Sheet)
请运行以下 Prompt，直到你刷出一个满意的形象：

> **Prompt:**
> `character sheet of a young asian female, 26 years old, round face, big clear eyes, messy hair, wearing a mix of comfortable linen clothes and high-tech tactical gear, wearing one pair of sleek smart glasses on face, sitting posture, standing posture, close up of face, white background, neutral lighting, consistent character design --no multiple glasses, sunglasses on head --ar 16:9`

**设计要点（你可以修改 Prompt 中的形容词）：**
*   **年龄**：`26 years old` (打工人的同龄人)。
*   **面部**：`round face` (圆脸) + `big clear eyes` (明亮大眼) -> 亲和力与灵气。
*   **服装**：`linen clothes` (棉麻/自然) + `tactical gear` (机能风/科技) -> 冲突感。
*   **配饰**：`wearing one pair of sleek smart glasses` (强调只戴一副) + `--no multiple glasses` (反向提示词)。

### 2. 固定角色 (Locking the Character via `--cref`)
当你选定了一张满意的角色设定图：
1.  放大 (Upscale) 该图。
2.  右键 -> **Copy Link**。
3.  在未来生成人物时，加上：`--cref <图片链接> --cw 100` (完全复制) 或 `--cw 10` (只复制脸，换衣服/动作)。

---

## 第三步：组合生成 (The "Cyber Walden" Formula)

现在你有了画风链接 (Sref URL) 和角色链接 (Cref URL)，这是你的**万能生成公式**：

```text
/imagine prompt: [场景描述] + [动作描述] --cref [角色链接] --cw 10 --sref [画风链接] --sw 100 --ar 9:16
```

**示例 (生成第一集画面)：**
> `wide shot of a man sitting on a wooden pier, legs dangling in water, looking at a giant holographic moon, peaceful night, fireflies --cref https://url-to-character --cw 10 --sref https://url-to-style --sw 100 --ar 9:16`

---

## 💡 进阶技巧：如何寻找现成的 `--sref` 代码？
如果你不想自己炼图，可以直接使用社区验证过的“风格代码” (Style Codes)。你可以去 Twitter (X) 或 Midjourney 官网搜索 "Midjourney sref codes"。

**为你推荐几个适合“赛博自然”风格的随机代码（你可以尝试撞大运）：**
*   `--sref 185987625` (胶片感+自然)
*   `--sref 4200676449` (极简冷淡风)
*   `--sref 3698242444` (高对比度电影风)

**操作：** 直接在 Prompt 后加 `--sref 185987625` 试试效果。

---

## 场景扩展库：未来城市 (Future City Expansion)
这是一套与“赛博自然主义”画风一致的未来城市场景，**强调赛博朋克的科技感与霓虹美学**，自然元素仅作为点缀。**使用时请记得加上你锁定的 `--sref <链接>` 以保持画风统一。**

### 1. 城市全景 (Cityscape) - 霓虹丛林
> **Prompt:**
> `wide cinematic shot of a massive futuristic cyberpunk city, towering skyscrapers piercing the clouds, dense holographic advertisements and neon lights in blue and pink, flying cars traffic, dry surfaces, high-tech infrastructure, hyper realistic, 8k, blade runner aesthetic, cinematic lighting, intricate details, sharp focus, octane render, unreal engine 5, masterpiece, high fidelity, global illumination --no rain, water --ar 16:9 --stylize 250`

### 2. 街道特写 (Street View) - 钢铁与光影
> **Prompt:**
> `street level view of a busy cyberpunk city, narrow alleyway filled with complex pipes and cables, glowing neon signs, steam rising from vents, futuristic shops and food stalls, dark and moody atmosphere with vibrant light accents, photorealistic, 8k --no rain, puddles --ar 16:9`

### 3. 人群与生活 (Urban Life) - 赛博公民
> **Prompt:**
> `cinematic shot of diverse people walking in a high-tech cyberpunk street, wearing futuristic fashion and cybernetic implants, surrounded by holographic interfaces and drone delivery bots, busy night market, neon lights, detailed crowd, 8k --no rain, umbrellas --ar 16:9`

### 4. 载具与机械 (Vehicles & Mechs) - 移动堡垒
**未来汽车设计稿 (Vehicle Design Blueprints - Multiple Angles):**
> **Prompt (通用公式):**
> `vehicle design sheet of a futuristic cyberpunk [VEHICLE_TYPE], studio lighting, multiple angles including front view, side view, back view, and isometric view, sharp angular design, [COLOR] body with neon accents, technical annotations, blueprint style, high resolution, 8k --no rain --ar 16:9`

**1. 赛博越野车 (Cyber Off-road SUV):**
> **Prompt:**
> `vehicle design sheet of a futuristic cyberpunk off-road SUV, heavy duty tires, reinforced chassis, roof rack with sensor array, studio lighting, multiple angles: front, side, rear, isometric, tactical camouflage finish, neon accents, technical blueprint style, 8k --no rain --ar 16:9`

**2. 极速跑车 (Hyper Sportscar):**
> **Prompt:**
> `vehicle design sheet of a futuristic cyberpunk hypercar, extremely low profile, aerodynamic body, scissor doors, glowing engine bay,  studio lighting, multiple angles: front, side, rear, top down, vibrant dual-tone finish, neon strips, industrial design concept, 8k --no rain --ar 16:9`

**3. 豪华轿车 (Luxury Sedan):**
> **Prompt:**
> `vehicle design sheet of a futuristic cyberpunk luxury sedan, long wheelbase, suicide doors, smooth curves mixed with sharp edges, studio lighting, multiple angles: front, side, rear, 3/4 view, premium metallic finish, elegant light lines, automotive design sketch, 8k --no rain --ar 16:9`

**4. 城市公交 (Future Bus):**
> **Prompt:**
> `vehicle design sheet of a futuristic cyberpunk city bus, articulated body, large glass canopy, autonomous sensor pods, studio lighting, multiple angles: front, side, rear, interior layout, modern city transit color scheme, public transit design concept, 8k --no rain --ar 16:9`

**巨型机甲 (Mecha):**
> **Prompt:**
> `low angle shot of a massive industrial mech robot standing in a maintenance bay, heavy metal texture, hydraulic pipes, warning lights, sparks flying from welding repairs, tiny human engineers for scale, industrial sci-fi atmosphere, 8k --ar 16:9`

### 5. 室内空间 (Interiors) - 科技与生活的结合
**高科技公寓 (Cyber Apartment):**
> **Prompt:**
> `interior shot of a futuristic apartment, floor-to-ceiling windows overlooking the neon city skyline at night, minimalist furniture with glowing edges, holographic computer terminal, messy cables, cozy but high-tech, ambient lighting, 8k --ar 16:9`

**黑客工作室 (Hacker Workspace):**
> **Prompt:**
> `cluttered workbench in a dimly lit room, multiple monitors displaying code and schematics, disassembled robot parts, soldering iron, empty energy drink cans, cool blue monitor glow illuminating the room, cyberpunk hideout vibe, detailed textures, 8k --ar 16:9`

**飞船驾驶舱 (Spaceship Cockpit):**
> **Prompt:**
> `pov shot from inside a spaceship cockpit, complex dashboard with hundreds of buttons and holographic displays, view of a nebula or planet through the windshield, worn leather seat, realistic sci-fi controls, star wars aesthetic mixed with cyberpunk, 8k --ar 16:9`

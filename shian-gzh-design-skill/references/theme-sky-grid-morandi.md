# 公众号排版组件库 —— 浅蓝网格莫兰迪

> **使用说明**：本组件库是 Shian 的备用浅蓝主题，只在用户明确要求浅蓝网格或蓝紫重点时使用。它参考浅色网格正文的白底、柔灰正文和低饱和重点词。
>
> **设计风格**：浅蓝格纸、莫兰迪蓝紫、柔灰文字、低饱和、正常文章感。适合 AI 工具教程、飞书/效率工作流、知识整理、个人方法论、轻量观点和温柔随笔。默认不要做顶部圆框、封面大卡、导读卡；网格只是衬托，正文应该像一篇清爽的公众号文章。
>
> **微信兼容铁律**：所有样式使用内联 `style`；所有文字节点用 `<span leaf="">` 包裹；不用 `<div>`、`class`、`id`、`position`、`float`、`display:grid`、CSS 变量、外部字体。

---

## 设计变量速查表

```
主色调：       #6FA8DC（柔天蓝）
强调色：       #8E7CC3（莫兰迪蓝紫）
浅蓝背景：     #F7FBFF
网格线：       rgba(191,215,241,0.42)
浅蓝块：       #EEF6FF
浅紫块：       #F3F0FA
浅黄点睛：     #FFE9A6
标题色：       #4F545C
正文色：       #666B73
次要文字：     #8A9099
辅助文字：     #AEB7C2
边框色：       #DDEAF7
浅分割线：     #EAF2FA
正文字号：     16px
正文行高：     2
全局行高：     1.85
字间距：       0.2px
最大宽度：     677px
内容区边距：   0 18px
圆角：         正文默认 0；图片/真实素材可少量 8px；不要做圆框和胶囊
阴影：         默认不用；只在图片等真实媒体需要浮起时少量使用
```

字体栈：`-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif`

正文关键词下划线权威样式以 `theme-index.md` 为准：

```css
border-bottom:2px solid #BFD7F1;font-weight:700;color:#7E6BB6;
```

---

## 各组件完整 HTML

### 组件 1 全局容器 grid-paper-shell

```html
<section style="max-width:677px;margin:0 auto;background:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#666B73;line-height:1.85;letter-spacing:0.2px;overflow-x:hidden;">
  <section style="padding:28px 18px 34px;background-color:#FFFFFF;background-image:linear-gradient(rgba(191,215,241,0.42) 1px,transparent 1px),linear-gradient(90deg,rgba(191,215,241,0.42) 1px,transparent 1px);background-size:26px 26px;border-radius:0;">
    <span leaf=""><br></span>
  </section>
</section>
```

使用时把所有正文组件放进第二层格纸 `section` 内。格纸只做浅背景，不再给每段套重卡片。

### 组件 2 文章标题 plain-article-title

```html
<section style="margin:0 0 30px;padding:6px 2px 0;">
  <p style="margin:0;font-size:28px;font-weight:900;line-height:1.35;color:#4F545C;letter-spacing:0;">
    <span leaf="">{{主标题前半}}</span><span style="color:#7E6BB6;border-bottom:3px solid #BFD7F1;"><span leaf="">{{蓝紫强调词}}</span></span>
  </p>
  <p style="margin:6px 0 0;font-size:28px;font-weight:900;line-height:1.35;color:#4F545C;letter-spacing:0;">
    <span leaf="">{{主标题后半}}</span>
  </p>
  <section style="width:56px;height:3px;background:linear-gradient(90deg,#6FA8DC,#B8A7DC);border-radius:99px;margin:16px 0 12px;">
    <span leaf=""><br></span>
  </section>
</section>
```

标题就是标题，不要给标题套圆角大卡、半透明大块或额外口号。公众号外部已经有标题时，也仍然只保留一个简洁的正文内标题，不再添加顶部引导。

### 组件 3 顶部轻提示 focus-strip（非默认）

默认不要使用这个组件。只有用户明确要求“顶部关注引导”“账号提示条”时才可用，而且不要做圆框胶囊。

```html
<section style="margin:0 0 26px;padding:0 0 0 12px;border-left:3px solid #BFD7F1;">
  <p style="margin:0;font-size:13px;color:#8A9099;line-height:1.8;">
    <span leaf="">{{轻提示文案}}</span>
  </p>
</section>
```

### 组件 4 简洁目录 plain-toc

```html
<section style="margin:0 0 32px;padding:0 0 0 2px;">
  <p style="margin:0 0 12px;font-size:12px;font-weight:800;color:#6FA8DC;letter-spacing:2px;text-transform:uppercase;">
    <span leaf="">READING MAP</span>
  </p>
  <p style="margin:0 0 8px;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;color:#7E6BB6;font-weight:900;margin-right:8px;"><span leaf="">01</span></span><span leaf="">{{看点一}}</span>
  </p>
  <p style="margin:0 0 8px;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;color:#7E6BB6;font-weight:900;margin-right:8px;"><span leaf="">02</span></span><span leaf="">{{看点二}}</span>
  </p>
  <p style="margin:0;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;color:#7E6BB6;font-weight:900;margin-right:8px;"><span leaf="">03</span></span><span leaf="">{{看点三}}</span>
  </p>
</section>
```

目录是可选组件。文章本身层次清楚时可以省略；不要为了“设计感”硬加导读卡。

### 组件 5 开头引言 intro-note

```html
<section style="margin:0 0 32px;padding:18px 0 18px 16px;background:rgba(247,251,255,0.72);border-left:4px solid #BFD7F1;">
  <p style="margin:0;font-size:17px;font-weight:800;line-height:1.9;color:#4F545C;">
    <span leaf="">「{{引言正文，核心词可用蓝紫强调}}」</span>
  </p>
  <p style="margin:10px 0 0;font-size:13px;color:#AEB7C2;text-align:right;">
    <span leaf="">{{署名或省略}}</span>
  </p>
</section>
```

### 组件 6 章节标题 gentle-chapter

```html
<section style="margin:46px 0 24px;">
  <p style="margin:0 0 6px;font-size:12px;font-weight:800;color:#AEB7C2;letter-spacing:2px;text-transform:uppercase;">
    <span leaf="">PART {{01}}</span>
  </p>
  <p style="margin:0;font-size:25px;font-weight:900;line-height:1.35;color:#4F545C;letter-spacing:0;">
    <span style="color:#6FA8DC;"><span leaf="">{{小符号}}</span></span><span leaf="">{{中文标题}}</span>
  </p>
  <section style="width:100%;height:1px;background:linear-gradient(90deg,#BFD7F1,rgba(191,215,241,0));margin-top:12px;">
    <span leaf=""><br></span>
  </section>
</section>
```

小符号按文章气质轻量选择，如 `✦`、`⌁`、`01`。如果用户喜欢截图里的 emoji 感，可以少量使用一个 emoji，但不要每段都放。

### 组件 7 正文段落 paper-paragraph

```html
<p style="margin:0 0 18px;font-size:16px;line-height:2;color:#666B73;font-weight:500;">
  <span leaf="">{{普通正文}}</span><span style="color:#7E6BB6;font-weight:800;border-bottom:2px solid #BFD7F1;"><span leaf="">{{重点短语}}</span></span><span leaf="">{{后续正文}}</span>
</p>
```

重点短语的来源：写文章时与用户交互确认；若用户没有标注，按信息密度选择，普通过渡段可不标，单段最多 2 个。不要整段变紫，也不要把每个名词都加粗。

### 组件 8 蓝紫加粗 emphasis-inline

```html
<span style="color:#7E6BB6;font-weight:800;border-bottom:2px solid #BFD7F1;"><span leaf="">{{加粗重点}}</span></span>
```

Markdown 的 `**文字**` 默认映射到这个组件，而不是普通黑色加粗。

### 组件 9 淡蓝高亮 soft-highlight

```html
<span style="background:linear-gradient(transparent 58%,#DCEBFA 58%);color:#5F82B8;font-weight:800;"><span leaf="">{{高亮文字}}</span></span>
```

Markdown 的 `==文字==` 默认映射到这个组件。它比大色块更像截图里的轻标记。

### 组件 10 金句引用 soft-quote

```html
<section style="margin:8px 0 26px;padding:16px 0 16px 16px;background:rgba(243,240,250,0.58);border-left:4px solid #B8A7DC;">
  <p style="margin:0;font-size:17px;font-weight:850;line-height:1.9;color:#6F63A7;">
    <span leaf="">「{{金句或核心判断}}」</span>
  </p>
</section>
```

### 组件 11 轻提示 note-card

```html
<section style="margin:4px 0 26px;padding:14px 0 14px 16px;background:rgba(238,246,255,0.58);border-left:4px solid #BFD7F1;">
  <p style="margin:0 0 6px;font-size:13px;font-weight:800;color:#6FA8DC;letter-spacing:1px;">
    <span leaf="">{{提示标签}}</span>
  </p>
  <p style="margin:0;font-size:15px;line-height:1.9;color:#666B73;">
    <span leaf="">{{提示正文}}</span>
  </p>
</section>
```

这是辅助框的默认形态：左竖线 + 浅底。不要做圆角大框、胶囊标签、描边卡片。辅助框只用于真正需要停顿的关键判断、补充解释或反常识提醒，不能每节都放。

### 组件 12 步骤/清单 step-list

```html
<section style="margin:0 0 24px;">
  <p style="margin:0 0 12px;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;margin-right:10px;color:#6FA8DC;font-weight:900;"><span leaf="">01</span></span><span leaf="">{{步骤或清单内容}}</span>
  </p>
  <p style="margin:0 0 12px;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;margin-right:10px;color:#7E6BB6;font-weight:900;"><span leaf="">02</span></span><span leaf="">{{步骤或清单内容}}</span>
  </p>
  <p style="margin:0;font-size:16px;line-height:1.8;color:#666B73;">
    <span style="display:inline-block;margin-right:10px;color:#B18A2F;font-weight:900;"><span leaf="">03</span></span><span leaf="">{{步骤或清单内容}}</span>
  </p>
</section>
```

### 组件 13 图片框 image-soft-frame

```html
<section style="background:rgba(255,255,255,0.82);border-radius:18px;padding:8px;border:1px solid #DDEAF7;box-shadow:0 10px 26px -22px rgba(111,168,220,0.65);margin:4px 0 10px;">
  <section style="margin:0;border-radius:10px;overflow:hidden;">
    <span leaf=""><img src="图片URL" style="max-width:100%;height:auto;display:block;margin:0 auto;"></span>
  </section>
</section>
<p style="font-size:12px;color:#AEB7C2;text-align:center;margin:0 0 24px;">
  <span leaf="">— 图片说明文字</span>
</p>
```

无说明文字时删除下方说明段。

### 组件 14 素材占位 material-placeholder

```html
<section style="margin:4px 0 26px;padding:26px 20px;border:1px dashed #C9DDF2;background:rgba(247,251,255,0.78);text-align:center;">
  <p style="margin:0 0 8px;font-size:24px;line-height:1;">
    <span leaf="">✦</span>
  </p>
  <p style="margin:0;font-size:14px;font-weight:800;color:#8A9099;">
    <span leaf="">待补素材</span>
  </p>
  <p style="margin:8px 0 0;font-size:13px;color:#AEB7C2;line-height:1.7;">
    <span leaf="">{{此处插入的图片、截图、录屏或 GIF}}</span>
  </p>
</section>
```

### 组件 15 作者签名 soft-signature

```html
<section style="margin:44px 0 0;padding:18px 0 0;border-top:1px solid #DDEAF7;">
  <p style="margin:0 0 8px;font-size:16px;font-weight:800;color:#4F545C;line-height:1.8;">
    <span leaf="">我是 {{作者名}}，{{一句话简介}}</span>
  </p>
  <p style="margin:0;font-size:15px;color:#8A9099;line-height:1.9;">
    <span leaf="">如果你觉得今天这篇有收获，欢迎点赞、在看、转发，我们下篇见。</span>
  </p>
</section>
```

---

## 完整文章模板骨架

使用本主题时按下面顺序装配：

1. `grid-paper-shell` 全局容器。所有正文组件放进第二层格纸 section。
2. `plain-article-title` 简洁文章标题。不要在标题上方添加圆框、胶囊、关注提示、英文口号或封面大卡。
3. 若开头有引用块，放 `intro-note`；如果没有引用，直接进入正文第一段。
4. 若文章特别长且用户需要导读，可放 `plain-toc`；默认不加目录卡。
5. 按章节循环：`gentle-chapter` → `paper-paragraph` / `step-list` / `soft-quote` / `note-card` / 图片组件。
6. 结尾用 `soft-signature`，且全文只出现一次。

装配节奏：这套主题靠格纸背景和段落呼吸感建立风格，不要把每个段落都包进卡片。正文段落占主体，标题和章节标题承担结构，不用额外“装饰性解释模块”。

---

## 内容节奏

这套主题的核心不是“好看组件”，而是帮文章把意思说清楚。默认按这个节奏组织：

1. **标题定方向**：标题直接说清本文要解决什么问题，允许一个蓝紫重点词，不加外层卡片。
2. **开头抛问题**：用 2-4 个自然段说明读者为什么需要看下去；有金句才用 `intro-note`，没有就直接正文。
3. **章节推进**：每个 `##` 是一个清晰动作或判断，不要写空泛标题。章节标题用数字/短英文标签承接结构，正文负责解释。
4. **重点打钉**：按信息密度标记，默认每 100–150 字约 1 处，单段最多 2 个。重点词应是判断、概念、方法、结果，不是普通名词。
5. **辅助框克制使用**：`note-card` 和 `soft-quote` 只在需要读者停一下的地方出现；一篇 1500-2500 字文章通常 2-4 个辅助框就够。
6. **结尾收束**：结尾回到一个可记住的判断或行动，不要再增加新的装饰模块。

视觉只是把节奏显出来：标题、章节号、横线、重点词、少量辅助框。不要为了显得“设计过”而增加额外容器。

---

## 文章类型 → 组件组合配方表

| 文章类型 | 核心组件 | 点缀组件 | 注意 |
|---|---|---|---|
| AI 工具教程 / 飞书效率流 | `plain-article-title`、`gentle-chapter`、`paper-paragraph`、`step-list` | `note-card`、通用代码块、`material-placeholder` | 默认不要顶部圆框、封面卡、导读卡。重点词用蓝紫，不用黑色粗体压迫正文。 |
| 知识整理 / 方法论拆解 | `plain-article-title`、`intro-note`、`gentle-chapter`、`paper-paragraph` | `soft-quote`、`note-card` | 保持格纸阅读感，少用硬卡片。 |
| 轻量观点 / 个人随笔 | `plain-article-title`、`intro-note`、`paper-paragraph`、`soft-quote` | `gentle-chapter`、`soft-signature` | 章节标题可以更短，留白更多。 |
| 清单 / 工具盘点 | `plain-article-title`、`step-list`、`paper-paragraph` | `plain-toc`、`image-soft-frame`、`note-card` | `plain-toc` 仅在清单很长时使用；不用圆角目录卡。 |
| 数据复盘 / 案例说明 | `plain-article-title`、`gentle-chapter`、`paper-paragraph` | `note-card`、通用表格或图片组件 | 数据用蓝紫/浅蓝强调，避免红色预警感。 |

---

## Markdown → 组件映射规则表

| Markdown 元素 | 映射组件 |
|---|---|
| `# 标题` | `plain-article-title` 简洁正文标题 |
| 开头 `> 引用` | `intro-note` |
| 非开头 `> 引用` | `soft-quote` |
| `## 标题` | `gentle-chapter`，编号按顺序生成 |
| 普通段落 | `paper-paragraph` |
| `**文字**` | `emphasis-inline`，蓝紫加粗下划线 |
| `==文字==` | `soft-highlight`，淡蓝底高亮 |
| `<u>文字</u>` / `++文字++` | 使用 theme-index 的正文下划线 CSS |
| `- 列表` / `1. 列表` | 信息量少时转为普通段落；步骤型、清单型用 `step-list` |
| 代码块 / 行内代码 | 优先用 `common-components.md` 的代码块和行内代码，主色替换为 `#6FA8DC` |
| 图片 / GIF | 图片优先用 `image-soft-frame`；GIF 可用通用 GIF 组件，色值替换为浅蓝/蓝紫 |
| `【插入...】` 待补素材 | `material-placeholder` |
| 作者签名 / CTA | `soft-signature`，全文仅一处 |

---

## 风格禁区

- 不要使用大面积正红、纯黑、深灰商务块作为主要视觉。
- 不要把所有内容都做成卡片；格纸背景本身就是主题。
- 不要默认生成顶部圆框、胶囊关注条、封面大卡、英文口号、额外 slogan。用户的文章本来就有标题，正常呈现标题和正文即可。
- 不要把“把 AI 接进真实生活/真实工作流”这类解释性口号硬塞进版面；只有原文真的写了才保留。
- 不要把辅助框做成大圆角卡片；辅助信息默认用左竖线、浅底、正文式呈现。
- 不要为了视觉变化强行加目录、贴纸、标签、徽章、图标；文章节奏清楚时，纯标题和正文就是最好的排版。
- 不要用高饱和渐变、荧光色、厚重投影。
- 不要让重点词全段变紫；普通过渡段可以不强调。
- 不要为了可爱而堆 emoji；小符号只做轻点缀。

# 主题索引与选择决策表

本表是主题信息的**单一来源**。工作流第 1 步据此向用户展示选项，第 2 步据"组件库文件"列读取对应库，下划线标记时据"正文下划线 CSS"列取值。

每个主题的**英文标识**（用于产物命名 `{中文名}({标识}).html`、Agent 引用）= "组件库文件"列去掉 `theme-` 前缀与 `.md` 后缀。展示给用户仍用中文名。

## 已注册主题

| 主题 | 主色 | 适用场景 | 组件库文件 | 正文下划线 CSS |
|------|------|---------|-----------|---------------|
| 青瓷绿稿纸 | `#7A9D8C` 青瓷绿（配陶土棕 `#A56F54`） | Shian 默认优先主题。适合 AI 方法论、知识整理、效率复盘、个人工具体系。清淡稳定、耐读，避开浅蓝 + 蓝紫参考图撞色。 | `references/theme-shian-sage-paper.md` | `border-bottom:2px solid #CADBCD;font-weight:700;color:#8B5E49;` |
| 暖杏手记 | `#D7A06B` 暖杏（配陶橘 `#C56F58`） | 适合个人观察、轻观点、成长复盘、生活化 AI 使用记录。温暖但不花哨。 | `references/theme-shian-apricot-notes.md` | `border-bottom:2px solid #EBCBAA;font-weight:700;color:#A85F4B;` |
| 铅笔灰稿纸 | `#767B82` 铅笔灰（配旧金 `#B89B55`） | 适合产品分析、系统说明、工具评测、偏理性的观点文。灰阶承重，少量旧金点题。 | `references/theme-shian-graphite-pencil.md` | `border-bottom:2px solid #D8D0B5;font-weight:700;color:#8C753E;` |
| 苔绿砂纸 | `#6F8068` 苔绿（配砂陶 `#B07A57`） | 适合案例复盘、长期主义、组织方法、认知类文章。比青瓷绿更沉稳。 | `references/theme-shian-moss-sand.md` | `border-bottom:2px solid #D4DEC6;font-weight:700;color:#8F644A;` |
| 珊瑚米白 | `#D9827C` 低饱和珊瑚（配玫瑰灰 `#9B6F88`） | 适合轻观点、个人品牌、创作复盘、面向大众的解释型文章。更有人味但不贴纸化。 | `references/theme-shian-coral-cream.md` | `border-bottom:2px solid #F0C9C2;font-weight:700;color:#8A5C72;` |
| 浅蓝网格莫兰迪 | `#6FA8DC` 柔天蓝（配蓝紫 `#8E7CC3`） | 旧参考备用主题。由于和用户参考图色彩接近，不再默认使用；仅在用户明确想要浅蓝网格 / 蓝紫重点时使用。 | `references/theme-sky-grid-morandi.md` | `border-bottom:2px solid #BFD7F1;font-weight:700;color:#7E6BB6;` |
| 清新工具绿 | `#059669` emerald | 教程、测评、清单、工具盘点（卡片丰富、信息密度高） | `references/theme-tool-green.md` | `border-bottom:2px solid #A7F3D0;font-weight:600;` |
| 红白色系 | `#DC2626` 正红 | 深度分析、观点、力量感话题（经典编辑风，编号章节+引言卡+签名区，红色克制点睛） | `references/theme-red-white.md` | `border-bottom:2px solid #FECACA;font-weight:600;` |
| 石墨极简风 | `#52525B` 石墨灰 | 设计、科技评论、专业观点、高端品牌（极简克制、留白理性、全灰阶） | `references/theme-graphite-minimal.md` | `border-bottom:2px solid #52525B;font-weight:600;` |
| 留白禅意风 | `#4A5D52` 墨绿 | 禅意冥想、极简生活、深度随笔、艺术留白（呼吸感最强） | `references/theme-zen-whitespace.md` | `border-bottom:1.5px solid #B5C8BC;font-weight:500;` |
| 清新票据风 | `#059669` emerald | 测评、工具对比、创意评测（票据/门票视觉隐喻，星级评分+编号+硬阴影卡片） | `references/theme-tool-ticket.md` | `border-bottom:2px solid #A7F3D0;font-weight:600;` |
| 橄榄手记 | `#1e1f23` 墨黑（配橙 `#ed7b2f`） | 内刊手记、深度评测、案例复盘、系统性说明文档（编辑部内刊质感，分节形式多样，信息密度偏高） | `references/theme-olive-journal.md` | `border-bottom:2px solid #ed7b2f;font-weight:600;` |

## 选择建议

- **Shian 默认制**：用户没指定主题、或说"直接排/一键排"时，默认使用第一行"青瓷绿稿纸"，或按文章内容在前 5 个 Shian 内容型主题中自动选择。不要默认使用"浅蓝网格莫兰迪"，它和参考图太接近，只作为备用。
- 用户明确想换风格时，再把本表全部主题列给用户选（中文名 + 适用场景），最贴合题材的主题可标"（推荐）"放第一位。
- 全自动模式（用户明说"直接排"）才自动选：默认第一行主题，题材明显契合其它主题时选契合项并在交付时说明理由。
- 同一篇文章只用一套主题，不混搭。

## 下划线色值的权威性

正文关键词下划线一律用上表"正文下划线 CSS"列的值。组件库里可能有浅色下划线变体，那是可选样式；**正文关键词标记以本表为单一权威来源**，避免双轨。

## 新主题登记流程

1. 把主题组件库写入 `references/theme-{英文标识}.md`（格式要求见 SKILL.md「添加新主题的规范」）。
2. 在上表登记一行；首个/最常用主题放第一行作为默认推荐。
3. 跑 `python3 scripts/component_lint.py .` 确认 0 ERROR。

> 用户想要全新风格时，可走 `references/theme-generator.md` 的自定义主题生成流程：按偏好/参考图生成区块库（预览存 `assets/theme-previews/`），确认后转标准主题库并按上面流程登记。

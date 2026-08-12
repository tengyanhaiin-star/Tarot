# Tarot · 塔罗牌

一个运行于浏览器的塔罗牌占卜模拟器，支持电脑与手机端。

## 功能

### 六种牌阵

| 牌阵 | 张数 | 用途 |
|------|------|------|
| 单张 | 1 | 专注当下，获取一条指引 |
| 三牌阵 | 3 | 揭示过去、现在、未来 |
| 圣十字 | 10 | 凯尔特十字，最深邃的完整解读 |
| 马蹄阵 | 7 | 分析情境全貌 |
| 五芒星 | 5 | 五大元素（灵、火、土、水、风）的指引 |
| 关系阵 | 6 | 洞察两人之间的能量 |

### 78 张完整牌组

- 22 张大阿卡纳（Major Arcana）
- 56 张小阿卡纳（权杖、圣杯、宝剑、星币各 14 张）
- 每张牌均有正位与逆位解读（50% 概率逆位）

### 位置语境解读

同一张牌在不同牌阵、不同位置上，会显示与该位置相关的解读文案，而非仅使用牌面通用含义。

解读分为 **8 类**，由位置标签自动匹配：

| 类别 | 适用位置标签 | 数据文件 |
|------|--------------|----------|
| generic（通用） | Your Message、过去、现在、未来、当下、你、Ta | 内置于 `index.html` |
| axis（轴/隐藏） | 上方、下方、隐藏、灵 Spirit | `pos-readings-axis.js` |
| hope（希望/指引） | 希望、指引、火 Fire、土 Earth、水 Water、风 Air | `pos-readings-hope.js` |
| act（建议/行动） | 建议、行动 | `pos-readings-act.js` |
| challenge（挑战） | 挑战 | `pos-readings-challenge.js` |
| outcome（结果） | 结果 | `pos-readings-outcome.js` |
| external（外部） | 外部 | `pos-readings-external.js` |
| bond（连结） | 连结 | `pos-readings-bond.js` |

**五芒星阵的特殊规则：** 火 / 土 / 水 / 风 四个元素位上的小阿卡纳解读，按**位置对应的元素花色**选取文案（火→权杖、土→星币、水→圣杯、风→宝剑），与抽到的牌面花色无关，避免「火位抽到圣杯却显示水元素」的错位。大阿卡纳仍使用该牌独立的 major 解读。

### 交互方式

- 抽牌后，所有牌背面朝上发出
- 点击「翻开下一张」，依次逐张翻开，保持仪式感
- 全部翻开后出现「导出 ✦」，可将本次解读生成为 PNG 图片保存
- 鼠标悬停已翻开的牌可查看放大预览（电脑端）
- 点击已翻开的牌可进入解读（电脑端）
- 点击「解读 ✦」查看所有已翻开牌的完整解读
- 点击「再次抽牌」在同一副牌中重新抽取（不重新洗牌）
- 点击「重置」重新洗牌，回到初始状态

## 使用方法

**在线访问：** 用浏览器打开 [塔罗牌](https://tengyanhaiin-star.github.io/Tarot/) 即可。

## 技术说明

- 纯 HTML + CSS + JavaScript，无框架与 npm 依赖
- 字体：[Noto Serif SC](https://fonts.google.com/noto/specimen/Noto+Serif+SC)（需联网加载）
- 位置解读由 `composeMeaning(card, positionLabel)` 根据 `LABEL_CLASS` 映射选取对应文案库
- PNG 导出使用 Canvas 绘制，含牌面缩略图、位置、牌名、正逆位与解读正文，文件名带时间戳
- 适配电脑与手机端，手机端仅支持竖屏

## 图片来源

塔罗牌图片来自 [freepngimg.com：Deck of French Tarot Playing Cards](https://freepngimg.com/svg/153970-deck-of-french-tarot-playing-cards)，许可证：CC0 1.0 Universal。

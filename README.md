# 🔥 SlangSnap · 美国网络热词趣味词典

一个纯前端、零依赖的单文件网站，搜罗美国互联网当红热词（rizz、skibidi、habibi、cooked……），用中英双语讲清楚每个词的意思、用法、例句和来历。

A zero-dependency, single-file web app that collects trending US internet slang, with bilingual (EN/中文) explanations, examples, and origin stories.

---

## ✨ 功能 Features

| 功能 | 说明 |
|---|---|
| 📚 词库 | 40 个热词，涵盖当红热词 / 脑腐专区 / 梗文化 / 经典常青 / 情感日常 5 大类 |
| 🔍 实时搜索 | 支持按英文词、中文含义、英文释义模糊搜索 |
| 🗂️ 分类筛选 | 点击分类标签一键过滤 |
| 🎲 随机抽词 | "Random / 随机" 按钮，抽一个惊喜词条 |
| 📖 词条详情 | 点击卡片弹出详情：中文意思、英文释义、例句（带翻译）、词源背景 |
| 🌐 中英切换 | 右上角一键切换 EN ⇄ 中文，默认英文，偏好自动记忆 |
| 📱 响应式 | 桌面 / 手机自适应布局 |
| 🏷️ 热度标签 | 🔥 Hot（爆火）/ 📈 Rising（上升）/ 🌳 Classic（常青）/ 🧠 Brainrot（脑腐） |

## 🚀 使用方法 Usage

无需安装、无需服务器，双击打开即可：

```
us-slang/index.html
```

或用浏览器直接打开该文件（`file://` 路径也可正常运行）。

## 🧩 词库数据结构 Data Format

词库内置于 `index.html` 底部的 `WORDS` 数组中，新增词条按以下格式追加即可：

```js
{
  term: "rizz",              // 词条（唯一，作为弹窗词源的索引键）
  emoji: "😏",               // 图标
  pron: "/rɪz/ 里兹",        // 音标 + 中文谐音
  cat: "trending",           // 分类: trending / brainrot / meme / classic / life
  heat: "hot",               // 热度: hot / rising / classic / brainrot
  trend: "Word of the Year 2023",  // 趋势标签（显示在徽章上）
  zh: "撩人技巧、个人魅力",   // 中文含义
  en: "Charisma, especially...",  // 英文释义
  example: "Bro has unlimited rizz...",  // 英文例句
  tr: "这哥们魅力值拉满……",   // 例句中文翻译
  origin: "由 Kai Cenat 带火……"  // 中文词源背景
}
```

英文词源写在 `ORIGIN_EN` 对象里，键与 `term` 对应：

```js
const ORIGIN_EN = {
  "rizz": "Popularized by streamer Kai Cenat ...",
  // ...
};
```

> 注意：新增词条时，`term` 与 `ORIGIN_EN` 的键必须完全一致，否则英文模式下会回退显示中文词源。

## 🌐 语言切换逻辑 i18n

- 界面文案集中在 `STR` 对象（`STR.en` / `STR.cn`）
- 分类名、热度标签均为 `{ en, cn }` 双语言结构
- 语言偏好存入 `localStorage`（键名 `slangsnap-lang`）；沙箱环境下自动降级为默认英文，不会报错

## 📝 说明 Notes

- 词库内容仅供娱乐与语言学习，热度数据为人工标注，非实时接口
- 单文件架构，复制 `index.html` 即可部署到任何静态托管（GitHub Pages / Netlify / Vercel）

---

Made with ❤️ by **g-uno**

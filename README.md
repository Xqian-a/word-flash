# 速记 Word Flash

> 黑白极简 · 批量速记 · 左键认识 · 右键查释

一个纯粹的英语单词速记工具。没有花哨的 UI，没有登录注册，没有广告。打开就背，关掉就走。

**[在线使用](https://xqian-a.github.io/word-flash/)**

## 核心玩法

每页 20 个单词铺满屏幕，快速扫描：

- **左键点击** → 标记为认识，卡片滑出，原位显示淡色释义
- **右键点击** → 翻转查看完整释义和词性
- **右键已认识的卡片** → 撤回为不认识
- **上一批 / 下一批** → 自由翻页，不需要全部标记完

不认识的词自动归入「不熟」分类，可反复复习直到记住。

## 功能一览

| 功能 | 说明 |
|------|------|
| 批量导入 | 粘贴文本、上传 CSV/TXT 文件，支持 PDF 原文格式 |
| 中文释义 | 内置四级核心 1500 词词典，其他词自动翻译 |
| 顺序/随机 | 按词汇表顺序背诵或打乱随机 |
| 导出单词本 | 三种模式：正常单词本、默写本（只有释义）、自测本（只有单词） |
| 数据备份 | 导出/导入 JSON，跨设备同步学习进度 |
| 离线使用 | 纯前端，无需服务器，本地打开即可 |

## 快速开始

### 在线使用

直接访问 **[xqian-a.github.io/word-flash](https://xqian-a.github.io/word-flash/)**

### 本地使用

```bash
git clone https://github.com/Xqian-a/word-flash.git
cd word-flash
# 直接用浏览器打开 index.html
```

## 词表导入

支持三种格式，每行一个单词：

**纯单词**
```
abandon
ubiquitous
ephemeral
```

**单词 + 释义（Tab 分隔）**
```
peril	n. 严重危险
confess	v. 承认；坦白
murder	n. & v. 谋杀
```

**PDF 原文（自动解析序号和音标）**
```
1. peril [ˈperəl] n. 严重危险
2. confess [kənˈfes] v. 承认；坦白
```

项目自带 `cet4_core_words.txt`（四级核心 1500 词），可直接上传导入。

## 项目结构

```
word-flash/
├── index.html          # 主应用（单文件，含全部 HTML/CSS/JS）
├── dict_data.js        # 内置中文词典数据（1459 词）
├── cet4_core_words.txt # 四级核心词汇表
└── README.md
```

零依赖，零构建，单个 HTML 文件即完整应用。

## License

[MIT](https://opensource.org/licenses/MIT)

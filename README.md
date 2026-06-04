# 单词速记 Word Flash

> 黑白极简 · 批量速记 · 左键认识 · 右键查释

一个纯粹的英语单词速记工具。没有花哨的 UI，没有登录注册，没有广告。打开就背，关掉就走。

<img width="2840" height="1534" alt="image" src="https://github.com/user-attachments/assets/23a13922-ab52-4eac-9d63-239ea755a576" />

**[在线使用](https://word-flash.xqian.top/)** → 部署于github pages

## 核心用法

每页 20 个单词铺满屏幕，快速扫描：

- **左键点击** → 标记为认识，卡片滑出，原位显示淡色释义
- **右键点击** → 翻转查看完整释义和词性，同时播放发音
- **右键已认识的卡片** → 撤回为不认识
- **上一批 / 下一批** → 自由翻页

不认识的词自动归入「不熟」分类，可反复复习直到记住。

<img width="2840" height="1534" alt="image" src="https://github.com/user-attachments/assets/4f68bd7e-9fb9-498e-967f-3fb70b3bbba0" />

<img width="2840" height="1534" alt="image" src="https://github.com/user-attachments/assets/9d3def99-de29-4427-9718-355ea93f20ef" />

## 功能一览

| 功能 | 说明 |
|------|------|
| 批量导入 | 粘贴文本、上传 CSV/TXT 文件，支持 PDF 原文格式 |
| 中文释义 | 内置 14600+ 词中文词典，其他词自动翻译 |
| 单词发音 | 右键翻转自动发音，支持自定义音色、语速、音高 |
| 顺序/随机 | 按词汇表顺序背诵或打乱随机 |
| 导出单词本 | 三种模式：正常单词本、默写本（只有释义）、自测本（只有单词） |
| 数据备份 | 导出/导入 JSON，跨设备同步学习进度（含发音设置） |
| 离线使用 | 纯前端，无需服务器，本地打开即可 |

<img width="2840" height="1534" alt="image" src="https://github.com/user-attachments/assets/051e0fba-c5d9-4983-95b9-740de3f1bab1" />

## 发音设置

使用浏览器内置 SpeechSynthesis 引擎，支持：

- **音色选择** — 系统所有可用音色，支持搜索和收藏
- **语速调节** — 0.5x ~ 1.5x
- **音高调节** — 0.5 ~ 2.0
- **静音开关** — 一键切换静音/发音
- **设置持久化** — 发音设置随数据备份一起导出

<img width="2840" height="1534" alt="image" src="https://github.com/user-attachments/assets/55cedad0-f99b-4b34-a4f4-4afe83518e76" />

## 内置词典

`dict_data.js` 内置 **14624 个单词**的中文释义和词性，覆盖以下词表：

| 词表 | 词数 |
|------|------|
| 初中词汇 | 3223 |
| 高中词汇 | 6008 |
| 四级词汇 | 7508 |
| 六级词汇 | 5651 |
| 考研词汇 | 9602 |
| 托福词汇 | 13477 |
| SAT 词汇 | 8887 |
| **去重后合计** | **14624** |

内置词典中的单词查词时直接返回中文释义，无需联网。

## 使用的 API

对于不在内置词典中的单词，应用会依次尝试以下免费 API（均无需注册、无需 API Key）：

| API | 用途 | 说明 |
|-----|------|------|
| [dictionaryapi.dev](https://dictionaryapi.dev/) | 英文词典 | 获取词性和英文释义，作为兜底 |
| [MyMemory](https://mymemory.translated.net/) | 翻译 | 英译中，提供中文释义 |

查词优先级：内置词典 → MyMemory 中文翻译 → dictionaryapi.dev 英文释义

## 快速开始

### 在线使用

直接访问 **[word-flash.xqian.top](https://word-flash.xqian.top/)**

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
├── dict_data.js        # 内置中文词典数据（14624 词）
├── cet4_core_words.txt # 四级核心词汇表
└── README.md
```

零依赖，零构建，单个 HTML 文件即完整应用。

## License

[MIT](https://opensource.org/licenses/MIT)

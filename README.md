# 公开原创题库

这是应用使用的公开原创题库仓库。当前为 4 章、216 题，涵盖冠词形式与词间拼写、基础动词与存在表达、冠词、名词和形容词配合，配有讲解卡、练习与综合挑战。首位 `pub-c01-boundaries` 是新课程 C01；其余三章为既有公开内容，尚未按新课程重组，不应把这 4 章理解为新课程的前四章。完整语法覆盖仍在建设中，全部内容尚待人工法语审校。

内容已经过 AI 编写及独立 AI 复核，尚待人工法语审校；技术检查和 AI 复核不构成原创性、版权或教学质量认证。

## 清单

`manifest.json` 是唯一入口，结构固定为：

```json
{
  "schemaVersion": 1,
  "edition": "public",
  "chapters": [
    "chapters/pub-c01-boundaries.json",
    "chapters/pub-predication.json",
    "chapters/pub-articles.json",
    "chapters/pub-agreement.json"
  ],
  "expectedChapterCount": 4,
  "expectedQuestionCount": 216
}
```

- `edition` 必须为 `public`。
- `chapters` 是按显示顺序排列的章节 JSON 相对路径，必须位于本仓库内。
- `expectedChapterCount` 与 `expectedQuestionCount` 必须与实际内容一致。
- 增删内容后同步更新清单和两个计数。加载器仍支持合法空库（`[]`、`0`、`0`），但本仓库的真实公开内容测试现在要求非空。

## 内容约定

- 只接受原创或已获授权的内容；不得放入原书题目、扫描文字、书中例句或截图。
- 章节、关卡和题目 ID 一旦发布应保持稳定。
- 题目 schema 由应用仓库定义；新增内容前先在应用仓库运行校验和测试。
- 公开内容仓库不得包含应用代码、私有题库、密钥或本机路径。

## 维护

应用通过同级目录读取本仓库；如使用本机其他位置，通过应用提供的公开题库路径环境变量显式指定，不把机器路径写入本仓库。

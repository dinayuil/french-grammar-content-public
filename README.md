# 公开原创题库

这是应用使用的公开原创题库仓库。当前为 25 章、3846 题，配有讲解卡、练习与综合挑战，覆盖完整的 5 阶段大纲（C01—C25）。内容由 AI 参与生成，未经过人工法语审校。

内容由 AI 编写及独立 AI 复核，未经过人工法语审校；技术检查和 AI 复核不构成原创性、版权或教学质量认证。

## 许可

除另有标注外，本仓库的题目、答案、解析、讲解、课程编排及文档采用 [CC BY-NC-SA 4.0（署名—非商业性使用—相同方式共享 4.0 国际）](LICENSE)。在许可适用的范围内，可以署名后进行非商业分享与改编；分享改编内容时须使用相同许可、提供许可链接并说明修改。完整条款见 [Creative Commons 法律文本](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode.zh-hans)。

商业使用须另行取得相应权利人的授权，可通过本仓库 Issues 联系维护者。该公众许可不限制权利人将自己的内容用于官方收费应用或另行授权。本许可只授予许可方有权授予的权利，不使原本不受版权保护的内容产生版权。

应用代码由独立的应用仓库按 MIT 许可提供，不代表本题库也采用 MIT。提交内容贡献前，请先与维护者确认官方商业发行所需的授权；仅按本仓库的非商业许可提交，不自动授予官方商业使用权。

## 清单

`manifest.json` 是唯一入口，结构固定为：

```json
{
  "schemaVersion": 1,
  "edition": "public",
  "chapters": [
    "chapters/pub-c01-boundaries.json",
    "chapters/pub-c02-noun-phrases.json",
    "chapters/pub-c03-adjectives.json",
    "chapters/pub-c04-determiners.json",
    "chapters/pub-c05-present.json",
    "chapters/pub-c06-verbs.json",
    "chapters/pub-c07-negation-questions.json",
    "chapters/pub-c08-imperative-emphasis.json",
    "chapters/pub-c09-past-tenses.json",
    "chapters/pub-c10-object-pronouns.json",
    "chapters/pub-c11-pronominal-verbs.json",
    "chapters/pub-c12-demonstrative-possessive-indefinite.json",
    "chapters/pub-c13-future-conditional.json",
    "chapters/pub-c14-relative-clauses.json",
    "chapters/pub-c15-comparison-adverbs.json",
    "chapters/pub-c16-time-space-prepositions.json",
    "chapters/pub-c17-passive-voice.json",
    "chapters/pub-c18-verb-complements.json",
    "chapters/pub-c19-subjunctive.json",
    "chapters/pub-c20-complex-sentences.json",
    "chapters/pub-c22-aspect-modality.json",
    "chapters/pub-c23-discourse-markers.json",
    "chapters/pub-c24-lexical-constructions.json",
    "chapters/pub-c25-integration-review.json"
  ],
  "expectedChapterCount": 25,
  "expectedQuestionCount": 3846
}
```

- `edition` 必须为 `public`。
- `chapters` 是按显示顺序排列的章节 JSON 相对路径，必须位于本仓库内。
- `expectedChapterCount` 与 `expectedQuestionCount` 必须与实际内容一致。
- 增删内容后同步更新清单和两个计数。加载器仍支持合法空库（`[]`、`0`、`0`），但本仓库的真实公开内容测试现在要求非空。

## 内容约定

- 只接受原创或已获授权的内容；不得放入原书题目、扫描文字、书中例句或截图。
- 章节、关卡和题目 ID 一旦发布应保持稳定。唯一的例外是 2026-11-06 的关卡长度上限：每个练习关/挑战关最多 10 题，超过的关卡被拆成 `<原关卡>-<n>`（标题加 `（n）`），题目 ID 不变。
- 题目 schema 由应用仓库定义；新增内容前先在应用仓库运行校验和测试。
- 公开内容仓库不得包含应用代码、私有题库、密钥或本机路径。

## 维护

应用通过同级目录读取本仓库；如使用本机其他位置，通过应用提供的公开题库路径环境变量显式指定，不把机器路径写入本仓库。

`main` 推送会通过 `repository_dispatch` 触发应用仓库的公开网页版部署与 APK 构建，使用本次推送的 commit SHA；应用仓库无需再手动更新内容 pin。dispatch 成功只表示事件已送达，实际部署结果需在应用仓库的 Actions 中查看。

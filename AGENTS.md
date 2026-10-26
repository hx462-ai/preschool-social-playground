# 项目协作约定

- kids-picture-book 用于故事分镜、角色视觉一致性和 SVG 插画。
- HTML Game Generator 负责产品整体交互和故事分支；此处仅记录职责，不代表已经安装该工具。
- 朗读由用户主动触发，默认关闭自动朗读。
- 当前任务仅安装和检查 skill，暂不开始产品开发。

## kids-picture-book 安装记录

- 来源：https://github.com/jingk1012-ux/picture-book-skill
- 来源提交：`a2eeaed0cf33db261a6af4e2bd76c71a20b7cc10`
- 身份：来源仓库根目录 `SKILL.md` 的 frontmatter 为 `name: kids-picture-book`，并由项目 `skills-lock.json` 记录同一来源。
- 项目级路径：`.agents/skills/kids-picture-book/SKILL.md`，以实际文件复制安装，非符号链接。
- 安装前检查：分支 `work`，HEAD 为 `1e78e93`，工作区干净；项目内无已有 skill，用户级现有 skill 的 name 均不匹配，也未发现同源安装。
- 安装命令（在项目根目录执行）：

  ```bash
  npx --yes skills add jingk1012-ux/picture-book-skill --skill kids-picture-book -a codex --copy --yes
  ```

- 本次新增完整来源文件：`SKILL.md`、`README.md`、`LICENSE`、`cover.png`、`assets/book_template.html`、`examples/book.json`、`references/svg_guide.md`、`scripts/build_book.py`；另新增本文件和 CLI 生成的 `skills-lock.json`。
- 无已有同源文件可复用，无缺失文件补齐；原项目 `README.md` 保留不变。全部 8 个来源文件均与上述提交逐字节一致。
- 后续检查须同时依据 SKILL.md 的 name 和来源识别，不只比较文件夹名。完整可用时直接复用，不重复下载、覆盖或主动升级；文件缺失时仅补齐缺失文件，保留本地修改。

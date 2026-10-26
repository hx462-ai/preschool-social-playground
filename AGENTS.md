# 项目协作约定

- kids-picture-book 用于故事分镜、角色视觉一致性和 SVG 插画。
- 产品为“幼儿园社交练习场”，面向家长与 3—6 岁儿童一对一共玩。
- Twine 用于梳理情境和故事分支；当前无需安装 Twine 桌面程序。
- HTML Game Generator 用于实现手机优先的 HTML 原型，负责产品整体交互及故事分支在页面中的呈现。
- 角色使用 SVG 插画表现。
- Colorfigures 仅按需要制作玩具、积木、桌椅等道具。
- 故事数据和分支逻辑独立于页面，便于后续迁移微信小程序。
- 每个选择均有自然的后续回应，允许暂停、退出和求助。
- 不设置分数、排行榜、倒计时、输赢判定或强制连续奖励。
- 朗读由用户主动触发，默认关闭自动朗读。
- 当前任务仅完成工具安装和检查，等待用户发出开始开发的指令。
- 以上用户约定优先于 skill 中通用的计分、胜负、奖励、自动音频和单文件组织建议；源码中的故事数据与分支逻辑保持独立，后续如需单文件交付可在打包时内嵌。

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

## HTML Game Generator 安装记录

- 来源：https://github.com/buildfastwithai/gen-ai-experiments/tree/main/skills/html-game-generator
- 来源提交：`7b6204328701d5a4d80dc02f81dc3ef8de483e9d`
- 安装前：分支 `work`，HEAD 为 `7b4b89d`，工作区干净；已检查项目级和用户级 SKILL.md 的 name，未发现 html-game-generator 或 colorfigures 的本地安装。原有 kids-picture-book 完整保留，未重复安装或升级。
- 已在项目根目录运行：

  ```bash
  npx --yes skills add buildfastwithai/gen-ai-experiments --skill html-game-generator -a codex --copy --yes
  ```

- 项目级入口：`.agents/skills/html-game-generator/SKILL.md`，frontmatter 为 `name: html-game-generator`；实际文件复制，非符号链接。
- 已读取来源及安装后的 SKILL.md，并阅读四份配套资料的目录与相关内容。安装保留来源子目录全部 5 个文件：SKILL.md 以及 `references/audio-recipes.md`、`references/engine-patterns.md`、`references/genres.md`、`references/visuals.md`，逐字节比对上述来源提交通过。
- 另补入来源仓库根目录 MIT `LICENSE`，与上述提交一致。该 skill 来源子目录本身没有 assets 或 scripts，不创建虚构的配套文件。
- 项目 `skills-lock.json` 新增同源条目；原有 kids-picture-book 条目保留。

## Colorfigures 安装记录

- 指定官方下载包：https://april-zhu.com/colorfigures/colorfigures.tar.gz
- 执行命令：

  ```bash
  curl --fail --show-error --location --connect-timeout 15 --max-time 60 https://april-zhu.com/colorfigures/colorfigures.tar.gz --output /tmp/colorfigures-official.tar.gz
  ```

- 下载失败：退出码 `22`，`curl: (22) The requested URL returned error: 403`。
- 诊断命令：

  ```bash
  curl --silent --show-error --location --head --connect-timeout 15 --max-time 30 https://april-zhu.com/colorfigures/colorfigures.tar.gz
  ```

- 诊断结果：代理响应 `HTTP/1.1 403 Forbidden`，退出码 `56`，`curl: (56) CONNECT tunnel failed, response 403`。受阻域名为 `april-zhu.com`，当前环境网络允许列表不包含该域名。
- 先前代理失败的诊断命令及错误见 Git 历史；该问题已通过本次用户提供的归档解决。
- 本次从用户提供的官方归档安装：`/tmp/codex-remote-attachments/01a1780d-5c36-7612-9a5e-f869ed49308f/4b619639-bb0a-4f8c-9964-bbfbb6675dca/1-colorfigures.tar.gz`。
- 下载包 SHA-256：`b74809acd591a7f209c8ba964b0b29bb050a953328aa6577581e6778d26257ff`。
- 安装前确认项目级、`~/.agents/skills`、`~/.codex/skills` 都没有 `colorfigures`，因此新建 `.agents/skills/colorfigures/`；未覆盖其他 skill。
- 归档完整性及路径检查通过：所有成员都在 `colorfigures/` 内，无绝对路径或 `..` 路径。安装后读取项目级 `SKILL.md`，frontmatter 为 `name: colorfigures`。
- 已保留归档中全部 8 个文件：`SKILL.md`、`README.md`、`LICENSE`、`assets/core.js`、`assets/examples/{claw,lamp,toaster}.html`、`scripts/build.py`。
- 当前开发准备完成；产品开发须等用户明确发出开始指令。

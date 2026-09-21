# 墨水舰队 — Happycapy 交接验证

本次唯一任务：完整导入现有项目、原样安装运行、真实浏览器试玩、完整源码与日志回收。没有新业务开发任务；禁止重做关卡、奖励、存档、画风或引擎。

## 确定基线
源工作树 `/Users/zhangbin/.codex/worktrees/ink-two-voyage/涂鸦海战`，分支 `codex/two-voyage-candidate`，源提交 `27eeb8662438f8c8014a1bd43a7a87ce8118731a`。导出时工作树干净，无未提交或未跟踪文件纳入。本包逐文件与源已验证；不含原 Git 历史。新实验仓库提交不同，另在回执记录。

README、agent.json 等包含历史工作树/版本说明；实际版本以本文件和 package.json、源提交为准，不切换到文档旧路径。历史绝对路径和研究外链仅为来源，不是运行依赖，也不授权读取其他目录或账户。平台必须仅在自己的独立云端目录工作，不调用已连接的本机桥接设备。

## 环境与实际命令
Node.js 26.x（源机器 26.0.0），JavaScript ES modules + Canvas 2D；Node HTTP/WebSocket 权威服务，node:sqlite 自动初始化/迁移独立数据库，无需外部数据库或 API Key。

```sh
node --version
npm ci
npm test
npm run check
PORT=4181 INK_DIRECTOR=deterministic INK_FLEET_DB=.data/happycapy-pilot.sqlite npm start
```

端口被占用就选独立空闲端口，不停其他服务。默认只监听 127.0.0.1，Host/Origin 校验只允许本机；不能关闭此校验或擅自绑定公网来获得云端预览。若没有账户内私有预览，留下原样服务/请求日志，交付回收包，本机验证；不得 Publish、开放链接/复制、部署公网。

`npm run build` 需独立实验 Git 初始提交与 tar，保留构建日志，不伪造源提交。若 ZIP 路径没有 Git，可先运行测试/启动，再仅在实验目录初始化一个干净基线。禁止读取凭据或访问别的仓库。

## 已有功能与未批准项
直接点击起航、A 倒退/D 前进（固定船头）、鼠标瞄准开火/F、空格墨水、P 暂停、Esc 设置、双语、船坞升级预览/购买及持久金币、单人/合作/决斗均已有实现。src/voyage-feedback.js 是最新事实反馈；最新交付记录 docs/v1/two-voyage-candidate.md。原有前两航区都是五波；第二航区“两段新结构”受关卡、结算和解锁冻结冲突阻塞，本次无授权实施。

奖励与经济仅称当前候选实现，不能称平衡验收或母版完全对齐。勋章、难度开放、通关结构等研究建议未批准，不转换成开发任务。原始源码未开放，参考派生素材无公开发行授权；用户仅批准本次私有交接实验，不公开分享。

## 文件与数据边界
运行资产：assets/visual-lock/manifest.json 及其选定图片、assets/fonts。AGENTS.md 与 PROJECT_CONSTITUTION.md 及最新用户范围共同适用；保留已有技能和许可。BUILD-MANIFEST.json 为原构建清单；HANDOFF-MANIFEST.json 为本次全包校验清单（不包含自身、运行生成物）。

排除：完整 Git 历史、真实 .data/存档/恢复码、node_modules、浏览器账户、原片/未选研究图片、录屏/output、缓存和其他项目。文档内旧本地路径不会随包读取或上传其目标。

## 原样运行与回收要求
先验证全部 HANDOFF-MANIFEST.json 文件 SHA-256，再 npm ci/test/check、启动，报告工作目录/Node 版本/文件数/实际退出码与日志。失败先留证，最多两轮针对具体证据的环境纠错；不升级依赖，不修业务。不得把预置静态图当游戏，不把平台自评当独立试玩。无外部模型、无新付费、无自动化/多智能体团队。

交付完整 ZIP，包含原源码/必要资产/锁文件/两清单，以及单独 evidence/（安装测试启动原始日志、变更清单、未验证项）。排除 node_modules、.data、凭据、平台账号配置。未改代码也应返回完整源码以验证往返，不制造空 PR。Codex 将回收到另一个干净目录逐文件对照、重新安装测试和本地试玩；不得合并或覆盖原项目。

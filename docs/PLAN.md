# 协作与分工计划

本仓库用于开发 Project Graph（graphif/project-graph）的扩展（插件）。长期项目，按下列分工协作。

## 角色

| 角色 | 职责 | 不做 |
| --- | --- | --- |
| ck（规划/验收） | 拆解需求、写规格与验收标准、维护路线图、审查并合并 PR、对用户汇报 | 不写业务代码 |
| gpt（主力开发） | 按规格实现扩展代码、提交 PR、修复审查意见 | 不自行改需求范围 |
| ds（子代理） | 调研 extprg-types API、写测试、做代码审查、补文档 | 不直接合并 |

## 工作流程

1. ck 在 GitHub Issue 中写需求：目标、范围、验收标准。
2. gpt 从 main 拉 feature 分支（feat/xxx），按 Conventional Commits 提交，开 PR。
3. ds 审查 PR、补测试与文档，把结论写在 PR 评论里。
4. ck 对照验收标准检查，通过后合并，并更新路线图。

## 约定

- 语言与工具链：TypeScript，pnpm，extprg 构建（build / dev / package）。
- API 以 extprg-types 为准，不猜接口；不确定先由 ds 调研并写入 docs/api-notes.md。
- 提交信息：feat: / fix: / docs: / refactor: / chore: 前缀。
- main 分支受保护：只通过 PR 合并。
- 每个扩展一个子目录或独立 Issue，避免互相影响。

## 路线图

- M0 脚手架（已完成）：官方 create-extprg 模板已推送。
- M1 确定首个扩展的功能与验收标准（等待用户）。
- M2 ds 调研所需 API，输出 api-notes.md。
- M3 gpt 实现首个扩展，ds 审查，ck 验收。
- M4 打包发布（extprg package），补 README 与 CHANGELOG。
- 之后：按 Issue 持续迭代。

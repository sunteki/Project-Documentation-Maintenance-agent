# Codex 项目维护 Agents(项目维护agents)

[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](LICENSE)

> 一套帮助 AI 代理(以及人类团队)在项目全生命周期内,把项目长期文档维护得准确、及时、结构清晰的规则与文档模板。

[**English README**](README.md)

## 这是什么

本仓库是一套**项目文档维护规则 + 模板工具箱**,供任何长期维护项目文档的人使用,尤其是 AI 编码代理。它回答这些问题:

- 动项目文档之前,应该先检查什么?
- 事实来源在哪里——当前代码、设计记录、Git 历史,还是旧会话?
- 哪份文档负责哪类内容(`README.md` / `architecture.md` / `decisions.md` / `known-issues.md` 等)?
- 文档什么时候该更新,什么时候应该刻意不动?
- 一次维护会话做到什么程度才算"完成"?

它包含两个部分。

### 1. `AGENTS.md` — 项目长期维护规则

代理在维护文档前和过程中阅读的精简规则集:

| 章节 | 内容 |
|---|---|
| 适用范围 | 本规则文件适用什么、**不授权**什么 |
| 维护前检查 | 编辑文档前要读取和核验什么 |
| 事实来源 | 代码/配置 > 架构与决策记录 > Git 历史;旧文档和旧会话只是线索 |
| 文档维护原则 | 只更新实际受影响的内容;不制造重复权威说明;未验证内容明确标注;敏感信息不进文档 |
| 文档职责 | 每份文档(`README`、`architecture`、`decisions`、`database`、`deployment`、`CHANGELOG`、`known-issues`)与内容职责的对照表 |
| 长期记录 | 决策、变更记录、已知问题的记录规范 |
| 删除和清理 | 未经明确确认,不得删除、移动或覆盖可能包含唯一信息的资料 |
| 维护完成标准 | 如何判断一次维护真正完成 |

### 2. `docs/templates/` — 文档模板

标准项目文档的模板集合,以及一个告诉代理"哪份文档打开哪个模板"的索引:

| 模板 | 用途 |
|---|---|
| `README.md.template` | 项目介绍、安装、运行和测试入口 |
| `architecture.md.template` | 模块、数据流、边界、部署拓扑 |
| `decisions.md.template` | 重要技术和产品决策(DEC-001, …) |
| `database.md.template` | 数据模型、迁移、数据安全 |
| `deployment.md.template` | 环境、部署步骤、验证、回滚 |
| `CHANGELOG.md.template` | 用户可见的版本变化 |
| `known-issues.md.template` | 当前未解决的问题和风险 |
| `session-index.md.template` | (可选)AI 会话与决策、文档的可追溯索引 |

## 目录结构

```
.
├── AGENTS.md               # 项目长期维护规则
├── docs/
│   └── templates/          # 项目文档写作模板
│       ├── INDEX.md        # 模板索引与使用规则
│       ├── README.md.template
│       ├── architecture.md.template
│       ├── decisions.md.template
│       ├── database.md.template
│       ├── deployment.md.template
│       ├── CHANGELOG.md.template
│       ├── known-issues.md.template
│       └── session-index.md.template
```

## 使用方法

1. 把 `AGENTS.md` 和 `docs/templates/` 目录复制到你的项目根目录。
2. 让 AI 代理在维护项目文档前先阅读 `AGENTS.md`——它界定了维护边界和"完成"标准。
3. 创建或更新文档时,让代理先打开 `docs/templates/INDEX.md`,只读取本次要动的那份文档对应模板。
4. 按项目实际情况调整规则;模板里的占位内容在填写之前不代表你项目的真实事实。

## 说明

- 本仓库**只有规则和模板**,没有需要构建、运行或测试的代码。
- 模板中的占位内容只是格式示例,不是当前项目事实。
- 不要把密钥、个人数据和不必要的敏感路径写进项目文档(见 `AGENTS.md`)。

## 许可证

[GPL-3.0](LICENSE) © sunteki
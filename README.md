# 知行交互规范 · Intent UI

本项目维护 `intent-ui` Skill，用于设计工作流程编排、后台业务功能取舍、组件交互设计、AI 设计方法约束与验收。正式 Skill 源码位于 `skills/intent-ui/`，开发过程中的临时产物放在项目根目录的 `artifacts/`。

## 目录结构

```text
intent-ui/
├── README.md                    项目目录与使用说明
├── .gitignore                   临时产物的 Git 忽略规则
├── skills/
│   └── intent-ui/               可独立安装或打包的完整 Skill
│       ├── SKILL.md             Skill 入口、触发范围与工作流程
│       ├── agents/
│       │   └── openai.yaml      显示名称与默认调用提示
│       └── references/          流程、方法、业务、组件、验收规则和来源资料
│           ├── tool-interface-style.md    工作台、控制台及配套展示面的风格规则
│           └── tool-interface-sources.md  NextLabs、LarkAgentX 案例与核验边界
└── artifacts/                   临时产物区，不属于 Skill
```

## 文件归属

| 位置 | 用途 | 安装或打包时是否包含 |
| --- | --- | --- |
| `skills/intent-ui/SKILL.md` | Skill 主指令 | 包含 |
| `skills/intent-ui/agents/` | Skill 界面元数据 | 包含 |
| `skills/intent-ui/references/` | 主指令引用的详细规范与来源 | 包含整个目录 |
| `artifacts/` | 调试、预览或工具运行产生的临时数据；内容可能为空 | 不包含 |
| `README.md`、`.gitignore` | 项目维护说明与版本管理配置 | 保留在项目中，不放入 Skill 包 |

`references/` 中的文件虽然不叫 `SKILL.md`，也属于 Skill 的正式内容，不应作为临时文件清理。

## 安装与调用

安装或分发时，取 `skills/intent-ui/` 这一个完整目录，保留其中的相对结构。复制后的 `intent-ui` 目录内应直接看到 `SKILL.md`，不要把整个项目根目录当作 Skill 包。

入口文档：[SKILL.md](skills/intent-ui/SKILL.md)。调用名称为 `$intent-ui`。

## 维护约定

- 修改规范时，以 `skills/intent-ui/` 中的文件为源码；本机已经安装的副本需要使用更新内容时再同步。
- 新增正式参考资料放入 `references/`，并从 Skill 入口或相关参考文件建立链接。
- 临时产物留在 `artifacts/`，不混入 `skills/intent-ui/`；清理前确认其中没有需要保留的交付文件。
- `.gitignore` 只在使用 Git 时忽略临时产物，不阻止目录生成。

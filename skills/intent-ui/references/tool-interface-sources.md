# 工具型界面风格来源

核验日期为 2026-11-08。适用于核对[工具型界面风格](tool-interface-style.md)中的案例短引用。NextLabs 与 LarkAgentX 均为产品实现案例。LarkAgentX 的令牌注释明确写了对 NextLabs 的借鉴关系，两者可用于观察迁移前后的取舍。

## 证据版本与范围

| 来源 | 核验方式 | 范围 |
| --- | --- | --- |
| [NextLabs 仓库](https://github.com/Next-AGI-Org/NextLabs) | 本地浅克隆 `main`，提交 `9907fb4bdd5d1c5bedc3d92369827d5e798217e1` | 使用 `apps/web` 当前前端与 `docs/design.md` 的设计记录。Git 克隆成功，网页检索返回 404，下方源码以本地克隆核对 |
| [NextLabs 部署](https://labs.openai-next.com/) | Chrome DevTools 截图、无障碍树、DOM 与 CSS 计算样式 | 桌面首页和工作台、命令面板、工作台窄屏与减少动效条件下可见的入口。部署未绑定到上述源码提交 |
| [LarkAgentX 仓库](https://github.com/cv-cat/LarkAgentX) | 本地浅克隆 `master`，提交 `cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b` | 使用 `webui/src` 以及 README 公布的演示入口 |
| [LarkAgentX 在线体验](https://larkagentx.cvcat.site/console) | Chrome DevTools 截图、无障碍树与浏览操作 | 桌面账号列表、概览、会话页。演示数据仅用于观察结构和状态呈现 |

## NextLabs

| 编号与证据类别 | 支持的观察 | 适配边界 | 定位 |
| --- | --- | --- | --- |
| `N1` 设计记录与线上首页 | 设计稿把高频工具面与成果展示面分开。线上首页可见衬线标题段落、轻点阵、作品拼贴与清楚的工作台入口 | 展示样式依赖成果浏览任务。动效强度、媒体归属与素材许可另行判断 | [设计方向](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/docs/design.md#风格方向)、[首页](https://labs.openai-next.com/) |
| `N2` 令牌与测试源码 | 浅灰面板包白色工作面，暗色主题重映射前景、表面与抬升。组件通过语义类消费令牌。测试扫描部分裸值并计算选定前景与背景叠加后的对比度 | 仅覆盖测试列出的组合及文件范围。目标项目令牌架构和无障碍验收沿用本 Skill 现有规则 | [令牌](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/apps/web/app/tokens.css)、[测试](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/apps/web/tests/tokens.test.ts) |
| `N3` 线上工作台与源码 | 宽屏可见模型选择、结果和参数。结果区可切换请求、代码和响应。无凭据时展示添加入口，运行按钮禁用。窄屏模拟仍能找到模型、视图、参数、提示词和运行入口。源码提供进阶参数折叠和执行快照视图 | 面板数量、默认模型、凭据流程与业务语义属于产品。只核验无凭据路径和窄屏入口可见性 | [线上工作台](https://labs.openai-next.com/play)、[工作台源码](https://github.com/Next-AGI-Org/NextLabs/tree/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/apps/web/components/workbench) |
| `N4` 线上命令面板与源码 | 页头有可见的搜索入口，打开后焦点进入搜索框。工作台和侧栏显示快捷键提示 | 具体组合键由平台、键盘布局和输入冲突决定。这里的观察覆盖打开和初始焦点 | [线上工作台](https://labs.openai-next.com/play)、[命令面板源码](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/apps/web/components/shell/command-palette.tsx) |
| `N5` 设计记录与样张源码 | 样张覆盖排版、表面、控件、状态、材质与运行效果，设计记录把重动效限定在展示面并要求减少动效时保留静止终态 | 样张与设计记录支持评审方式和意图。线上真实执行、所有动效及产品内部评分门槛各有自己的验证范围 | [设计系统](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/docs/design.md#设计系统)、[样张组件](https://github.com/Next-AGI-Org/NextLabs/tree/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/apps/web/components/specimen) |

NextLabs 的具体风格样本包括白底、浅灰工具面、弱分隔、中性反色主按钮、蓝色强调与独立状态色。正文使用 Geist 和中文系统黑体回退，展示标题结合 Instrument Serif 与 Noto Serif SC。线上首页还可见比早期草稿更多的顶栏导航项，当前布局以部署观察为准。 [设计记录](https://github.com/Next-AGI-Org/NextLabs/blob/9907fb4bdd5d1c5bedc3d92369827d5e798217e1/docs/design.md)、[线上首页](https://labs.openai-next.com/)

## LarkAgentX

| 编号与证据类别 | 支持的观察 | 适配边界 | 定位 |
| --- | --- | --- | --- |
| `L1` 令牌与样式源码 | 在浅底、弱边界、胶囊控件及前景层级上沿用 NextLabs 思路。主题重映射保留，强调色换为飞书蓝，状态色、图表系列与终端有各自令牌 | 可迁移的是表面和颜色的用途。品牌色、前景透明度、动效曲线与控件尺寸按目标产品核对 | [颜色令牌](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/styles/tokens.css)、[样式映射](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/styles/app.css) |
| `L2` 线上控制台与源码 | 壳层显示当前账号及概览、会话、设置、日志入口。概览把对象、状态与操作放在一起，指标合组，图表、近期记录分区。账号列表用文字区分运行中与需要重新登录 | 账号切换的路由规则、统计周期与具体运行操作仅适用该产品。在线观察不验证权限、存储或状态变更 | [在线体验](https://larkagentx.cvcat.site/console)、[控制台壳层](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/console/ConsoleApp.tsx)、[概览](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/console/Overview.tsx) |
| `L3` 线上会话与源码 | 桌面从概览进入会话页后，左侧可检索会话，右侧显示当前会话。源码在窄屏改为上下排列，等待用户选择，并区分无匹配与无会话 | 桌面选择行为来自线上观察。窄屏布局、空态分支来自源码。何时改为独立详情页、如何恢复列表，由目标项目验证 | [会话源码](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/console/Chats.tsx) |
| `L4` 设置源码 | 有未保存改动时出现保存入口，保存反馈区分是否已对运行中的账号生效 | 生效时间、失败处理与恢复方式取决于后端契约。本次未实测保存 | [设置源码](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/console/Settings.tsx) |

LarkAgentX 亮色壳层使用浅灰，账号工作区为白色。主题文件保留中性反色和独立强调色，控制台正文以无衬线呈现，衬线角色用在首次登录等少量引导标题。亮色主题下 NextLabs 与 LarkAgentX 均有中性色表面，具体的高亮颜色依各自品牌定义。 [令牌](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/styles/tokens.css)、[控制台壳层](https://github.com/cv-cat/LarkAgentX/blob/cfc1e0eeddf01401a9c3caa4f7e081e59725bd1b/webui/src/console/ConsoleApp.tsx)

## 令牌取值样本

下列取值来自固定提交的样式源码，用于定位两项目之间保留和改写的部分。各行记录的是令牌取值，具体页面还取决于应用位置和叠层。

| 令牌角色 | NextLabs | LarkAgentX |
| --- | --- | --- |
| 亮色底面 `bg` 与低层表面 `surface-1` | `#FFFFFF`、`#F4F5F7` | `#FFFFFF`、`#F4F5F7` |
| 亮色反色面 `invert` | `#0D0D0D` | `#0D0D0D` |
| 强调色 `accent`，亮色与暗色 | `#0A6FC2`、`#34A8EE` | `#3370FF`、`#5B8CFF` |

## 使用证据时的边界

- 引用设计记录时，保留它作为产品意图的身份。源码和部署有差异时分别记录所见。
- 引用在线状态时，按实际走查范围标注。此次未输入凭据、运行模型、登录账号、发送消息或保存配置。鉴权、权限、失败恢复及运行生命周期按各自契约验证。
- 要迁移具体模式时，先复查目标项目的任务、既有品牌与可访问性。色值、断点、字号、圆角、动效时长和快捷键按目标产品校验。
- 要复现视觉时，优先对照对应页面和固定提交的令牌。截图中的媒体、品牌素材和复制的代码片段有各自的授权边界。
- 需要把某项观察作为验收依据时，补上代表性的状态和输入方式。公开演示缺少条件时保留“仅源码”或“待实测”标记。

场景选择、角色映射、降级与复查条件均由本 Skill 定义。组件行为与可访问性验收分别按[组件交互设计语言](component-interaction-language.md)和[设计评估方法](design-evaluation.md)执行。

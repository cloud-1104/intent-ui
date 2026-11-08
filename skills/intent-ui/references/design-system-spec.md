# 设计系统与令牌规范

目录：令牌三层架构、令牌命名、主题与密度、组件规范文档模板、组件生命周期与准入、机器可消费格式、一致性审计。

适用条件：制定、重写或审查面向 AI 可消费的设计系统规范（令牌、组件文档、治理流程）时读取。本文件只管“规范如何书写与如何治理”，不承接具体界面的视觉美化请求：能力取舍见[能力判断](capability-decision.md)，具体组件的键盘、焦点与状态行为见[组件交互设计语言](component-interaction-language.md)，交付物格式与验收选取见[交付与检查](delivery-and-review.md)。各节“可省略／重新评估”条款为本 Skill 的裁量扩展，不出自所引体系。

## 令牌三层架构

产品存在设计令牌体系时，按三层组织。分层结构是对 Material 3（reference/system/component）、Carbon、SLDS（primitives/aliases/styling hooks）等多来源的综合提炼：各家词汇不同、分层一致，本表不是任何一家的官方术语，也不是联合标准。

| 层 | 职责 | 命名与取值 | 引用规则 |
| --- | --- | --- | --- |
| primitive | 原始值字典 | 允许描述值（blue-600、space-4） | 只被 semantic 层引用，组件不得直接引用 |
| semantic | 按用途分配值的“配电盘” | 描述意图（color-text-danger） | 引用 primitive；是组件取值的默认且唯一入口 |
| component | 单组件专属覆盖 | 绑定组件（button-primary-bg） | 例外而非默认；需书面理由才能创建 |

- 组件样式只引用 semantic 层。要建 component 令牌，必须书面写明该组件为何需要独立于全局语义变化，并记录重新评估条件；这项登记要求是本 Skill 扩展，不是来源原文。
- 单主题、单端产品可从 primitive+semantic 两层起步，component 层默认省略；出现第二个主题、品牌或端时重新评估分层。
- 令牌交换格式采用 [DTCG Format 2025.10](https://www.designtokens.org/tr/2025.10/format/)。身份要写准：它是 W3C Community Group Final Report，不在 W3C 标准轨；但 Figma、Style Dictionary、Tokens Studio 等工具链已支持，可作为事实标准的交换基线，引用时不得称其为“W3C 标准”。

## 令牌命名

semantic 与 component 层按意图命名，不按外观：color-text-danger，而非 color-text-red。四段式 namespace-object-base-modifier 以[新加坡政府 GDS 命名规范](https://www.designsystem.tech.gov.sg/foundations/token-naming)为直接范例，分类思想出自 [Nathan Curtis 的令牌命名体系](https://medium.com/eightshapes-llc/naming-tokens-in-design-systems-9e86c7444676)；此处综合为模板，不是两者的强制词表。

| 段 | 作用 | GDS 范例 sgds-primary-bg-emphasis 中的对应（按 GDS 原文分解） |
| --- | --- | --- |
| namespace | 系统或品牌前缀 | sgds |
| object | 作用对象或组件 | 省略；GDS 原文该例不含 object 段 |
| base | 属性类别 | primary-bg（角色+属性的组合段） |
| modifier | 状态、层级、密度等变体 | emphasis |

- 审查令牌命名的第一条检查：semantic/component 层名称是否泄漏视觉值（-red、-16px、-bold）。泄漏即退回重命名，否则换主题时名称与实际值矛盾。
- primitive 层允许以值命名（blue-600），该层职责就是值字典；不反过来要求 primitive 写意图。
- GDS 原文即允许省略 object 段、允许 base 为角色+属性的组合；省略段可行，但全库保持同一省略规则，同一含义不允许出现两种写法。

## 主题与密度

存在 light/dark、多品牌、密度档位或减少动态效果（reduced-motion）任一变体时 → 一律建模为 modifier 维度，切换只改 semantic→primitive 的映射。机制依据 [DTCG Resolver 2025.10](https://www.designtokens.org/tr/2025.10/resolver/)：sets 给令牌源分组，modifiers 为各维度声明可选 contexts 与 default，resolutionOrder 规定合并顺序，避免为“主题×品牌×密度”的每个组合手写一套令牌。

- 禁止组件层写死主题值：组件代码或 component 令牌里出现“dark 模式取 X”的分支即为实现错误，该分支应收敛进 semantic 映射。
- 映射示例（zeroheight 的 token modes 实践，属示例不属标准）：color-surface-default 在 light 下解析为 neutral-50、dark 下解析为 neutral-900；组件始终只写 color-surface-default。
- 单主题单密度产品可省略 Resolver 与 modifier 建模，直接给单一映射；重新评估条件：出现第二个主题、品牌或密度需求。
- 减少动态效果（reduced-motion）是否必需，依[组件交互设计语言](component-interaction-language.md)的动效条目判断，不以是否多主题为前提；存在该需求时在令牌层建模为 modifier 维度。

## 组件规范文档模板

为组件书写规范时覆盖下表小节。小节集合是对 Carbon（Usage/Style/Code/Accessibility 四 Tab）、Material 3（Specs、Accessibility）、Cloudscape（Features、Writing guidelines）、Atlassian、Polaris 文档结构的综合提炼；这些体系分页方式互不相同，本表不是它们的联合标准。

| 小节 | 必须写明 | 何时可省略 |
| --- | --- | --- |
| 示例预览 | 典型用法的可见示例 | 不省略 |
| 何时用／不用 | 适用与不适用场景；不适用时指向替代组件 | 不省略；确无替代组件时写明“暂无替代” |
| 解剖结构 | 组成元素的命名（container、label、icon 等） | 单元素组件可并入示例 |
| 变体×尺寸 | 变体与尺寸矩阵及各自选型条件 | 无变体且无尺寸档时省略 |
| 状态矩阵 | 逐元素×逐状态列出令牌取值 | 纯静态展示组件可缩减为默认态 |
| 行为细节 | 键盘、焦点、加载等行为契约 | 不复述规则，链接[组件交互设计语言](component-interaction-language.md)对应条目 |
| 内容指南 | 标签动词形式、大小写、占位文案 | 无文案元素时省略 |
| 无障碍 | 分列“组件已内建行为”与“使用者仍需完成的责任” | 不省略 |
| 变更记录 | 版本、破坏性变更、迁移说明 | 提案与实验阶段可只记关键决定 |

- 状态矩阵逐元素×逐状态给出令牌，设计 QA 才能机检；做法出自 [Carbon 组件 Style 页](https://www.carbondesignsystem.com/building-blocks/core/components/tabs/specifications)对每个元素列 enabled/hover/focus/disabled 取值。
- 无障碍小节引用量化门槛必须注明体系：如“容器对比 3:1、200% 字号下标签不超两行”是 Material 3 对自家组件的验收值，不得写成 WCAG 要求或普适标准、法定要求。
- 禁用态参考 M3 自家规则：用颜色与降低层次表达、不要求达到对比度、不可聚焦，且部分组件不允许禁用态——不可用就不渲染。是否采纳由业务按[能力判断](capability-decision.md)的操作可用性规则裁决；采纳不可聚焦方案时，必要的禁用原因仍须按[状态与业务流程](states-and-workflows.md)权限与只读小节的规则对键盘和触控用户可获取。

## 组件生命周期与准入

每个组件方案标注生命周期阶段。阶段模型综合 [USWDS component lifecycle](https://designsystem.digital.gov/components/lifecycle/) 与 Carbon 的 PDLC（Draft→Preview candidate→Preview→Stable），门槛表述以 USWDS 为主要出处，括号内的判定基准为本 Skill 的操作化扩展；USWDS 的 45 天公开评议是其自身节奏，不作为普适时限。

| 阶段 | 进入门槛 | 阶段内约定 |
| --- | --- | --- |
| 提案 | 先查复用：现有组件或组合不能满足；提案写明用户需求证据、预计复用场景、无障碍方案 | 评审通过前不进入开发 |
| 实验 | 功能完整（覆盖提案列明的复用场景）、代码达生产质量（以组件库 CI 通过为判据）、通过无障碍测试 | 允许破坏性变更，使用方须知悉风险 |
| 稳定 | 有生产使用记录、文档覆盖上表全部适用小节、需求全部达标（提案批准时列出的需求项逐条核销） | 破坏性变更走版本化与迁移说明；仍需周期性无障碍与可用性审计。把一致性审计纳入稳定期为本 Skill 扩展，见下文“一致性审计”节 |
| 废弃 | 决议废弃即标 Deprecated：保留代码、停止更新、给出迁移路径并通知使用方 | 迁移完成后 Retired 移出代码库；两步不可合并，禁止无声删除 |

- 提案评审结论四选一：批准、有条件批准（写明未就绪的依赖项）、退回补充论证、不予采纳；不存在默认通过。
- 治理有效以可观察信号判定：产品团队持续绕开官方路径自造组件即治理失效，此时先修流程瓶颈再谈组件质量；目标状态是走官方路径比自造更快、更可预测。
- 单团队单产品可合并提案与实验阶段；重新评估条件：出现第二个消费方团队时恢复完整流程。废弃两步走在任何规模下不省略。

## 机器可消费格式

规范面向 AI 与自动化工具消费时，下列为本 Skill 的扩展要求，非上述任何体系原文：

- 每个令牌条目同时给出已解析值与用途说明，不只给引用链；消费方不应为取一个值而遍历三层。
- 每个组件给出机器可读契约：必需的 ARIA 属性、全部状态的枚举、允许的 props 及取值范围。该契约是[交付与检查](delivery-and-review.md)“组件行为契约”面向自动化消费的序列化形式，只覆盖可静态机检的部分，字段映射到行为契约对应维度，不另立模板；键盘与焦点语义链接[组件交互设计语言](component-interaction-language.md)，不在契约里复述。

## 一致性审计

多团队或多端消费同一系统时，一致性审计为条件必需。方法为多来源综合提炼，不是任何一家的官方流程，来源登记见[流程、评估与设计系统来源](process-sources.md)：

1. 先定义权威参照物：批准稿、组件库、令牌还是验收标准。未定义“正确等于什么”之前，任何检查与自动化都不成立。
2. 按“单旅程全链路”执行：选一条关键用户旅程，沿令牌→设计稿→代码→文档→线上追踪分歧；不做全站截图盘点。
3. 每处分歧按[交付与检查](delivery-and-review.md)的评审发现结构记录（所在位置、观察证据、触发条件、用户后果、严重程度、最小修正、验收方式），审计记录在此基础上增加责任人与处置决定（修复／豁免／废弃）两个字段；增补字段为本 Skill 扩展。
4. 有正当理由的偏离登记为例外并入台账，写明理由与复查条件；不登记的例外按漂移处理。
5. 令牌值、颜色、间距、硬编码扫描等可机检项优先自动化；状态完整性、语义正确性与内容质量保留人工复核。

单团队单应用可把审计并入发布前检查，省略独立审计流程；重新评估条件：出现第二个消费端，或设计与代码开始由不同团队维护。

本文完整来源清单、核验日期与适配边界由[流程、评估与设计系统来源](process-sources.md)承载；正文只保留关键依据链接，不重复罗列。

# 流程、评估与设计系统来源索引

参考核验日期：2026-11-07。其中 DTCG Format、DTCG Resolver、GDS 命名、USWDS lifecycle 四页经当日在线核验；Microsoft UXR 页当日返回 403；其余条目依当期研究简报整理，不声称是最新版本。这里登记[设计工作流程](design-process.md)、[AI 设计思路](ai-design-method.md)、[设计评估方法](design-evaluation.md)、[设计系统与令牌规范](design-system-spec.md)四份文件实际依据的外部来源、各自支持的判断与适配边界；正文只保留短引用，断言与依据的对应以本表为准，四文件中的综合提炼不是这些来源共同发布的规范。

主题与正文的对应：流程模型、交付物与交接两节服务设计工作流程；评估与度量、无障碍标准服务设计评估方法；设计令牌与设计系统服务令牌规范；AI 设计工作流服务 AI 设计思路。组件模式与组件库来源见[组件来源与差异处理](component-sources.md)，Cloudscape 业务模式见 [Cloudscape 来源](cloudscape-sources.md)，不在此重复。

## 流程模型

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [ISO 9241-210:2019（ANSI 预览页）](https://webstore.ansi.org/preview-pages/ISO/preview_ISO+9241-210-2019.pdf) | 四核心活动骨架；迭代由评估驱动；退出条件是“设计方案满足已说明的用户需求” | 预览页不含完整条款，不等于核验全文；标准不提供具体方法，也不指导敏捷迭代切分 |
| [Design Council：Framework for Innovation](https://www.designcouncil.org.uk/resources/framework-for-innovation/) | 发散与收敛交替节奏；允许从任意阶段回退 | 它是操作手册；覆盖上线与持续运营（官方自称止步于小规模交付） |
| [d.school：Let's Stop Talking about THE Design Process](https://dschool.stanford.edu/stories/lets-stop-talking-about-the-design-process) 与 [NN/g：Design Thinking 101](https://www.nngroup.com/articles/design-thinking/) | 设计思维可从任意模式进入的非线性；d.school 公开反对把五步当唯一标准流程；NN/g 六阶段补 Implement 环节 | 设计思维可当交付管线；工作坊化与群体思维批评已被化解 |
| [GV Design Sprint](https://www.gv.com/sprint/) | 独立草图与结构化决策（反群体思维）的机制出处；五天日程与 5 名用户是该方法自身设定 | Sprint 适合小改进；5 名用户访谈是统计证明；前置条件可省略 |
| [NN/g：Design Process Isn't Dead, It's Compressed](https://www.nngroup.com/articles/design-process-isnt-dead/) | 专家压缩流程而非丢弃流程；按问题类型、风险与已知程度裁剪 | 三档路径划分出自该文（该划分为本 Skill 扩展）；压缩可以省略验证 |
| [Lean UX（O'Reilly 摘载）](https://www.oreilly.com/content/the-3-foundations-of-lean-ux/) 与 [SVPG：Dual-Track Agile](https://www.svpg.com/dual-track-agile/) | 假设绑定可测信号；未经验证的需求不进交付；Cagan 已弃用“双轨”一词 | 最小化文档适用于强合规环境；“双轨”指两个独立团队 |

## 交付物与交接

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [Jeff Gothelf：Lean IA](https://jeffgothelf.com/blog/lean-ia-getting-out-of-the-deliverables-business/) | 交付物只为回答未决问题而存在——统一省略判定问句的依据 | 文档越少越好是普适规则；该原则豁免验证义务 |
| [NN/g：Wireflows](https://www.nngroup.com/articles/wireflows/) | 页面少、状态多的应用用 wireflow；单独的线框或流程图都不完整 | wireflow 适用于所有产品形态；可替代旅程图等宏观交付物 |
| [NN/g：Creating Design Specs for Development（2025）](https://www.nngroup.com/articles/creating-design-specs-for-development/) | 规格六要素；规格在设计后期产出、小而及时；设计更新必须记录并通知接收方 | 六要素是行业强制标准；其工单拆分方式适用于一切协作形态 |
| [NN/g：UX Prototypes: Low vs. High Fidelity](https://www.nngroup.com/articles/ux-prototype-hi-lo-fidelity/) | 保真度三轴；按要验证的问题选保真度 | 低保真是一切任务的先行义务；特定保真度绑定特定阶段 |
| [NN/g：Personas vs. Jobs-to-Be-Done](https://www.nngroup.com/articles/personas-jobs-be-done/) | 问题陈述聚焦要完成的任务与期望结果（JTBD 式写法） | JTBD 可替代画像或用户研究 |
| Figma 交接指南：[Developer Handoff 手册](https://www.figma.com/blog/the-designers-handbook-for-developer-handoff/) 与 [Best Practices](https://www.figma.com/best-practices/guide-to-developer-handoff/) | 交接必写信息的实践基础；以设计系统与 token 为共享语言；不一致时以设计文件为准 | Dev Mode 工具链是必需配置；单一厂商实践等于行业标准 |

## 评估与度量

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [NN/g：Design Critiques](https://www.nngroup.com/articles/design-critiques/) 与 [Figma critique 实践](https://www.figma.com/blog/design-critiques-at-figma/) | 批评与评审分离；反馈锚定目标；静默浏览保持意见独立 | 议程环节与时长是唯一正确流程；单一公司实践等于行业标准 |
| [NN/g：How to Conduct a Heuristic Evaluation](https://www.nngroup.com/articles/how-to-conduct-a-heuristic-evaluation/) | 十条启发式；两遍法；独立评估后汇总去重 | 启发式通过等于可用性合格或法律合规；误报可以忽略 |
| [NN/g：Severity Ratings](https://www.nngroup.com/articles/how-to-rate-the-severity-of-usability-problems/) | 0-4 量表；频率、影响、持续性三因素；多人均值才可靠 | 单评估者评分可当精确测量；“3-4 级未闭环即阻断”出自该文（为本 Skill 收紧约定） |
| [NN/g：Cognitive Walkthroughs](https://www.nngroup.com/articles/cognitive-walkthroughs/) 与 [Userfocus 四问](https://www.userfocus.co.uk/articles/cogwalk.html) | 走查四步协议与可学习性定位；四问的简化表述 | 两版四问是同一官方文本；走查可替代真实用户测试 |
| [NN/g：Success Rate](https://www.nngroup.com/articles/success-rate-the-simplest-usability-metric/) | 任务成功率是最通用的行为指标；先定义可判定的成功判据 | 行业平均完成率可作本项目达标线 |
| [MeasuringU：Interpret SUS Score](https://measuringu.com/interpret-sus-score/) | SUS 用法与均值基准 68 的体系归属 | 68 是任意量表的通用及格线 |
| [Kerry Rodden：HEART](https://www.kerryrodden.com/heart/) | HEART 五维与 Goals-Signals-Metrics 推导法 | 五维必须全部度量；“后台慎用 Engagement 时长指标”出自该文（为本 Skill 适配） |
| 业界设计 QA 清单（OverlayQA、UX Atlas、Pixso、Notarus 等厂商页面） | QA 检查维度与 pass/fix/accepted-risk 三态的业界实践基础 | 任一清单是权威标准或完整集合；厂商博客可作规范性依据 |

## 无障碍标准

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [WCAG 2.2（W3C Recommendation）](https://www.w3.org/TR/WCAG22/) | 文本对比 4.5:1、UI 组件与图形 3:1、目标尺寸 24×24 等条款原文与级别 | 条款值可挪作通用设计阈值；抽查通过构成合规认证 |
| [What's New in WCAG 2.2（W3C WAI）](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/) | 2.2 新增条款清单与级别——后台最相关五条的出处 | 新增条款之外的 2.x 要求可以忽略 |
| [WCAG-EM（W3C WAI）](https://www.w3.org/WAI/test-evaluate/conformance/wcag-em/) | 五步抽样审计流程 | 抽样通过等于全站合规；WCAG-EM 新增符合性要求 |
| [WCAG 3 Timeline（W3C AGWG）](https://www.w3.org/WAI/GL/wiki/WCAG_3_Timeline) | WCAG 3 仍是工作草案、与 WCAG 2 长期并存——锚定 2.2 AA 的时效论证 | WCAG 3 的草案条款可提前当作验收基线 |
| [EN 301 549 V4.1.1（ETSI）](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/04.01.01_60/en_301549v040101p.pdf) | v4.1.1（2026-09）将 web 基线升至 WCAG 2.2 AA；OJEU 引用生效前法律基线仍是 v3.2.1 | 按 2.2 AA 验收即满足任一法域合规认证 |

组件级键盘与 ARIA 验收用例（APG 各模式 Keyboard Interaction 与 Roles, States, and Properties 两表）的来源登记在[组件来源与差异处理](component-sources.md)，不在此重复。

## 设计令牌与设计系统

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [DTCG Format 2025.10](https://www.designtokens.org/tr/2025.10/format/) | 令牌 JSON 交换格式；身份为 W3C Community Group Final Report，Figma、Style Dictionary、Tokens Studio 已支持 | 它是 W3C 标准轨规范；采用格式即自动获得工具链互通 |
| [DTCG Resolver 2025.10](https://www.designtokens.org/tr/2025.10/resolver/)，示例见 [zeroheight token modes](https://zeroheight.com/learn/token-modes-handling-variation-in-your-token-system/) | sets、modifiers、resolutionOrder 的多上下文解析机制；同一 semantic 令牌按模式解析为不同值的示例 | Resolver 是主题切换的唯一合法实现；示例取值是标准配色方案 |
| 令牌命名：[GDS Token naming](https://www.designsystem.tech.gov.sg/foundations/token-naming) 与 [Nathan Curtis](https://medium.com/eightshapes-llc/naming-tokens-in-design-systems-9e86c7444676) | 四段式 namespace-object-base-modifier 范例及原文分解；按意图命名的分类思想 | 四段必须齐全；两家词表适用于其他产品 |
| [Sujeet Jaiswal：令牌分层对照](https://sujeet.pro/articles/design-tokens-and-theming) | Material 3、Carbon、SLDS 词汇不同、分层一致的对照依据 | 三层术语出自任何一家官方文档 |
| 生命周期：[USWDS component lifecycle](https://designsystem.digital.gov/components/lifecycle/) 与 [Carbon 组件检查清单](https://www.carbondesignsystem.com/getting-started/contributing/component-checklist) | 提案→实验→稳定→废弃的门槛；PDLC 状态与设计/代码/测试/文档四轨验收 | 45 天评议是普适时限；准入表括号内判定基准归属来源（为本 Skill 扩展） |
| 文档结构：[Carbon Tabs Style](https://www.carbondesignsystem.com/building-blocks/core/components/tabs/specifications)、[Atlassian Button](https://atlassian.design/components/button/usage)、[Cloudscape 组件页](https://cloudscape.design/components/collection-select-filter/)、[Polaris Button](https://polaris-react.shopify.com/components/actions/button) | 逐元素×逐状态列令牌取值使 QA 可机检；组件文档小节集跨体系收敛 | 各家分页方式与小节命名可互换；小节集是联合标准 |
| [Material 3 Buttons accessibility](https://m3.material.io/components/buttons/accessibility) 与 [Applying states](https://m3.material.io/foundations/interaction/states/applying-states) | 容器对比 3:1、200% 字号两行内是 M3 自家验收值；禁用态用颜色与降低层次表达、不可聚焦、部分组件不渲染禁用态 | 这些门槛是 WCAG 要求、普适标准或法定要求 |
| 一致性审计：[Tcules](https://www.tcules.com/insights/guides/how-to-audit-a-design-system) 与 [21st.dev](https://docs.21st.dev/blog/design-system-consistency-audit)（未在线复核） | 先定义权威参照物；单旅程全链路追踪；例外登记台账；可机检项优先自动化 | 该方法是唯一正确审计流程；其工具链是必需配置 |

## AI 设计工作流

| 来源 | 直接支持的判断 | 不能据此推断 |
| --- | --- | --- |
| [Anthropic：Improving frontend design through Skills](https://claude.com/resources/articles/improving-frontend-design-through-skills) | 分布收敛的成因描述；“禁用默认＋具体替代＋防二次收敛”的写法原型 | 文中字体与配色示例是通用禁令；该写法适用于所有模型与产品风格 |
| 70% problem：[Addy Osmani 原文](https://addyo.substack.com/p/the-70-problem-hard-truths-about)（内引 Peter Yang） | AI 快速完成大部分首稿、剩余部分需专家判断的经验命名 | 70% 是实测比例；可当验收指标或完成度度量 |
| [NN/g：Testing AI Methodology](https://www.nngroup.com/articles/testing-ai-methodology/) | 四维评估框架（目标一致性、概念质量、视觉设计、交互与可用性）；prompt 具体度四级 | 该篇含实测结论；可作“LLM 做启发式评估”的实证依据 |
| [NN/g：AI Prototyping](https://www.nngroup.com/articles/ai-prototyping/) | 实测结论“远看可观、细节不足”；模糊 prompt 必然失败 | 所有工具存在固定能力上限或失败比例 |
| [arXiv：GPT-4o 启发式评估对比研究](https://arxiv.org/html/2506.16345) | LLM 查全率与抽象判断不及人类专家的实证；定位为补充而非替代 | 查全率数值是所有 LLM 的固定指标 |
| [Microsoft UXR（Medium）](https://medium.com/uxr-microsoft/why-ai-tools-are-not-ready-to-replace-human-heuristic-evaluations-yet-e56a143c0967) | “AI 尚不能独立做启发式评估，适合 hybrid 流程”——自评只作人审前初筛的定位 | 2026-11-07 访问返回 403；内容依研究简报摘录，不声称在线核验 |
| [Lockstep：给 AI 编码代理的设计上下文](https://www.getlockstep.dev/blog/ai-coding-agents-design-context) | 五层设计上下文（设计稿、组件映射、token、组件库文档、书面决策）；只给截图导致硬编码裸值与重复造组件 | 五层的降级动作与记录要求出自该文（为本 Skill 扩展）；其厂商方案是必需配置 |

## 哪些是本 Skill 的扩展

对照四份正文文件，下列内容为本 Skill 自有扩展，不得标注为上表任何来源的官方要求：

- [设计工作流程](design-process.md)：回退时记录触发原因；发散/收敛显式阶段标记；输出声明所走路径、跳过阶段及理由；验证覆盖空、错误与极端状态并要求验收含上线后可观察结果。
- [AI 设计思路](ai-design-method.md)：五层设计上下文的分层口径、降级动作与重新评估条件记录；状态完备性硬门槛的核对动作与“不适用须可复查”的结论口径。
- [设计评估方法](design-evaluation.md)：方法选取表及重新评估条件；评审意见协议四要素与三级映射；启发式 3-4 级未闭环即阻断交付的收紧约定；设计 QA 例外台账与复查条件。
- [设计系统与令牌规范](design-system-spec.md)：component 令牌书面登记要求；令牌条目同给已解析值与用途说明、组件机器可读契约；一致性审计纳入稳定期并增补责任人与处置决定字段；各节“可省略/重新评估”条款与准入判定基准。

四阶段骨架、最小交付物链与“三承载物”、失败模式五类、多 agent 分工、批评与评审议程、QA 检查维度、令牌三层表、文档模板小节集属多来源综合提炼：声明“不是联合标准”，不归属任何单一来源，引用时区分来源原意与本 Skill 扩展。

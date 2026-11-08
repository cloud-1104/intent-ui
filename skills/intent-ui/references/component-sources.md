# 组件来源与差异处理

参考核验日期：2026-10-31。这里记录各来源支持的判断及迁移边界；[组件交互设计语言](component-interaction-language.md)是综合提炼，不是这些项目共同发布的规范。需要具体 API、默认值或最新兼容性时再查对应版本。

## 五个来源各负责什么

| 来源 | 提取内容与直接依据 | 不能据此推断 |
| --- | --- | --- |
| WAI-ARIA APG | [使用前提](https://www.w3.org/WAI/ARIA/apg/practices/read-me-first/)说明角色需要实际行为支持；[键盘接口](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/)区分组件内外导航、焦点和选中 | APG 是实践指南；不是品牌设计体系，参考示例不等于跨设备验证或 WCAG 合规证明 |
| Carbon | [Button](https://www.carbondesignsystem.com/building-blocks/core/components/button/guidelines)提供动作层级；[Toggle](https://www.carbondesignsystem.com/building-blocks/core/components/toggle/guidelines)说明二元即时设置场景；[Tooltip](https://www.carbondesignsystem.com/building-blocks/core/components/tooltip/guidelines)限定补充信息和交互边界 | 不把它的按钮对齐、颜色、变体名称和大小要求普遍化；页面示例不能替代所选模式的语义核验 |
| Ant Design | [即时反应](https://ant.design/docs/spec/reaction/)支持动作前中后的适当反馈；[足不出户](https://ant.design/docs/spec/stay/)支持保留上下文、渐进展示和有条件的撤销 | 不是所有任务都应放在当前页或弹窗；减少确认不能覆盖高风险业务要求 |
| Radix Primitives | [Accessibility](https://www.radix-ui.com/primitives/docs/overview/accessibility)说明语义、焦点、键盘及标签责任；[Composition](https://www.radix-ui.com/primitives/docs/guides/composition)强调组合后保留 props、事件和 ref 所需能力 | 默认组件可访问不等于自定义包装仍正确；不强制选择 Radix 或特定 React API 写法 |
| React Aria | [Quality](https://react-aria.adobe.com/quality)关注输入方式、标签、本地化和可访问视觉；[usePress](https://react-aria.adobe.com/usePress)处理鼠标、触控、键盘和取消按压 | 不能仅换一个事件名就宣称支持所有设备；业务重复提交和异步成功仍需应用层处理 |

## 具体组件行为依据

| 模式 | 核验重点 |
| --- | --- |
| [Checkbox](https://www.w3.org/WAI/ARIA/apg/patterns/checkbox/) | Space 切换、组选中与 mixed 状态 |
| [Radio group](https://www.w3.org/WAI/ARIA/apg/patterns/radio/) | 互斥选择；普通组与工具栏内的方向键规则不同 |
| [Switch](https://www.w3.org/WAI/ARIA/apg/patterns/switch/) | 稳定标签、二元 checked 状态；Space 必需，Enter 可选 |
| [Combobox](https://www.w3.org/WAI/ARIA/apg/patterns/combobox/) | 区分自由输入和限定选值，输入与候选、确认与关闭的行为 |
| [Menu button](https://www.w3.org/WAI/ARIA/apg/patterns/menu-button/) | 打开菜单和焦点进入，后续使用菜单的键盘模式 |
| [Tabs](https://www.w3.org/WAI/ARIA/apg/patterns/tabs/) | 自动激活需要无明显延迟；手动激活用 Enter 或 Space |
| [Accordion](https://www.w3.org/WAI/ARIA/apg/patterns/accordion/) | 标题按钮、展开状态与内容关联；正常 Tab 顺序 |
| [Table](https://www.w3.org/WAI/ARIA/apg/patterns/table/) 与 [Grid](https://www.w3.org/WAI/ARIA/apg/patterns/grid/) | 普通表格可以包含控件；网格是需要内部焦点导航的复合控件 |
| [Modal dialog](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/) | 模态背景、初始焦点、内部 Tab 循环和关闭后的焦点恢复 |
| [Radix Dialog](https://www.radix-ui.com/primitives/docs/components/dialog) 与 [Popover](https://www.radix-ui.com/primitives/docs/components/popover) | 都可有模态和非模态配置；实现默认值不能代替业务对模态性的判断 |

## 不同建议如何取舍

1. **先确定意图和实际语义。** 同样的下拉外形可能是选择值、命令菜单或信息面板；先确定任务再查对应模式，不拼接互相矛盾的键位。
2. **先守住原生语义和可达行为，再适配产品。** 原生元素满足任务时无需手工重造；确需自定义则完整实现所选模式。APG 中可选项不是硬要求，库的扩展按既有一致性判断。
3. **按风险决定是否阻断。** Ant Design 鼓励在上下文中处理并在可能时撤销；不能恢复、影响严重时仍采用 Cloudscape 的风险分层。不要统一“所有删除确认”或“所有删除直接撤销”。
4. **保存时机独立于 ARIA 角色。** Carbon 倾向 Switch 即时生效；APG 的 switch 角色并不规定服务器保存时机。沿用产品约定时要让生效时间可理解；新设计默认优先消除开关与保存按钮的歧义。
5. **统一产品语言，不统一所有默认值。** 主次动作、危险性、焦点和错误的意义一致；颜色、位置、时间、组件 API 和动效参数沿用当前产品。不是把五个库装在一个页面上。
6. **用具体行为验证集成。** 标签补充、事件传递、焦点恢复和嵌套浮层经过自定义后重新检查；界面截图、组件名称或库宣传都不能独立证明键盘及辅助技术行为正确。

组件状态分层、输入法保护、嵌套 Esc、异步选项竞态、单次执行和跨组件一致性是本 Skill 的集成约定；不要将这些完整要求归因于某一个来源。只引用相关来源实际支持的部分。

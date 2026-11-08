# 来源与适配边界

参考核验日期：2026-10-31。以下为官方模式的简短索引和适配边界，未复制其完整文档或示例代码。引用具体规则或更新规范时，按需核验对应页面；离线使用摘要时不声称内容为最新。

本文件负责 Cloudscape 的业务模式来源；WAI-ARIA APG、Carbon、Ant Design、Radix 和 React Aria 的组件来源及差异处理见 [组件来源与差异处理](component-sources.md)。

## 官方模式索引

| 官方来源 | 直接支持的判断 |
| --- | --- |
| [Patterns](https://cloudscape.design/patterns/) | 用组件组合解决用户任务，覆盖资源管理与通用交互 |
| [Side navigation](https://cloudscape.design/patterns/general/service-navigation/side-navigation/) | 导航依据用户任务与信息架构组织 |
| [Service dashboards](https://cloudscape.design/patterns/general/service-dashboard/) | 根据监控、调查和信息获取目标选择仪表盘结构 |
| [Table view](https://cloudscape.design/patterns/resource-management/view/table-view/) | 用表格支持识别与比较，并处理加载、空态和错误 |
| [Filtering patterns](https://cloudscape.design/patterns/general/filter-patterns/) | 按查询复杂度选择文本、有限属性或组合属性筛选 |
| [Filter persistence](https://cloudscape.design/patterns/general/filter-patterns/filter-persistence-in-collection-views/) | 支持往返和分享筛选状态，避免在 URL 放敏感信息 |
| [Resource details](https://cloudscape.design/patterns/resource-management/details/) | 按任务与关联资源复杂度选择普通、标签或资源中心详情 |
| [Create resource](https://cloudscape.design/patterns/resource-management/create/) | 依据流程复杂度、长度与恢复需求选择创建容器 |
| [Edit resource](https://cloudscape.design/patterns/resource-management/edit/) | 按字段依赖和编辑任务选择整页或行内编辑 |
| [Global actions](https://cloudscape.design/patterns/general/actions/global-actions/) | 安排针对对象或集合的动作及状态操作 |
| [In-context actions](https://cloudscape.design/patterns/general/actions/incontext-actions/) | 让常用单对象操作靠近对象，按频率组织菜单 |
| [Delete patterns](https://cloudscape.design/patterns/resource-management/delete/) | 按严重性、恢复成本、依赖选择删除确认强度 |
| [Validation](https://cloudscape.design/patterns/general/errors/validation/) | 就地展示校验错误，帮助用户定位和纠正 |
| [Unsaved changes](https://cloudscape.design/patterns/general/unsaved-changes/) | 对可能丢失的未保存修改提供离开提示 |
| [Disabled and read-only states](https://cloudscape.design/patterns/general/disabled-and-read-only-states/) | 区分暂不可操作与仅可查看，并解释必要原因 |
| [Empty states](https://cloudscape.design/patterns/general/empty-states/) | 区分没有资源、没有匹配和空字段，错误不假装为空 |
| [Loading and refreshing](https://cloudscape.design/patterns/general/loading-and-refreshing/) | 根据上下文处理首次加载、刷新、旧数据和失败 |
| [Feedback mechanisms](https://cloudscape.design/patterns/general/user-feedback/) | 按消息范围及进度可计算性选择通知和加载反馈 |

辅助来源：[WAI-ARIA 模态对话框模式](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/)支持模态焦点和键盘规则。项目组件是否符合该模式需实际检查。

## 哪些是本 Skill 的扩展

- 基础必需、条件必需、可选增强、不适用和待确认的能力决策方法。
- 数据来源、状态、角色、依赖与风险共同决定功能取舍。
- 业务停用和恢复语义、版本发布和审批、并发冲突、多租户切换。
- 批量选择范围、部分提交、失败项重试、任务结果未知及取消语义。
- 导入导出、附件和操作历史的业务约定与验收模板。

这些内容用于把公开模式转化为后台工作规则，应根据业务事实验证。不要标为 Cloudscape 官方强制标准。

## 适配原则

- Cloudscape 面向资源管理的示例不决定某个业务是否允许删除、修改、审批或导出。
- 官方建议中的字段数、动作数量、布局和时间示例属于该体系语境。迁移到既有产品时保留决策依据，不自动替换已验证的设计系统。
- 当官方页面之间存在适用范围差异，优先核对具体模式及其条件。例如“允许提交以显示校验错误”不意味着执行中或高风险确认前也必须允许重复提交。
- 表单容器和消息样式可以使用现有组件库实现；不要求安装 Cloudscape，不默认 React，不重写品牌视觉。
- 只声称查验过的内容；来源不可用时采用明确标注的设计建议，不能编造官方结论或兼容性承诺。

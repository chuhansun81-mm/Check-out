---
name: checkout-operations-admin-design
description: 为 AT 收银台运营后台分析需求、生成、更新、评审与实现页面及交互。适用于收银台模板配置、商户支付产品配置、交易服务、待复核与复核记录、品牌与主题色、列表、查询、表单、详情、弹窗、拖拽排序、宽表格固定操作列，以及写入 Figma 或生成 HTML 原型；提到“收银台运营后台”“AT 管理平台”“蓝色版”“通用模板”“商户配置”“支付方式配置”时使用。
---

# AT 收银台运营后台设计

## 默认目标

将需求转成一致、可复核、可实现的后台页面。默认主色 `#1E75FF`；界面字体使用系统字体栈，macOS 优先苹方、Windows 优先微软雅黑。输入与反馈遵循 Arco Design 习惯。未明确要求时保留原业务术语、信息架构和已有页面。

## 执行流程

1. 读取需求、截图、现有 Figma 节点或 HTML，识别用户任务、页面类型、角色与状态。
2. 读取 [references/page-map.md](references/page-map.md)，确认页面在完整流程中的位置。
3. 读取 [references/visual-spec.md](references/visual-spec.md)，复用导航、栅格、字体、颜色和组件。
4. 按任务读取专项规则：
   - 列表、表单、详情：读取 [references/page-patterns.md](references/page-patterns.md)。
   - 主题色、拖拽、复核、删除：读取 [references/interaction-spec.md](references/interaction-spec.md)。
   - 字段与状态：读取 [references/domain-model.md](references/domain-model.md)。
5. 生成完整任务路径需要的默认态、操作态、确认态、错误态和结果态，不用说明文字替代核心交互。
6. 写入 Figma 时读取 [references/figma-workflow.md](references/figma-workflow.md)，同时遵循 `figma-use` 与 `figma-generate-design`。
7. 生成 HTML 时沿用现有项目结构，真实实现查询、展开、颜色应用、拖拽、弹窗和预览同步。
8. 交付前按 [references/acceptance-checklist.md](references/acceptance-checklist.md) 验收。

## 不可违背的业务规则

- 新增、修改、删除均进入待复核；复核通过后生效。
- 删除前先确认，确认后提交“删除待复核”，不可直接静默删除。
- 驳回复核时意见必填，最多 100 字；未填写时保持弹窗并显示行内错误。
- 支付方式按列表顺序展示；第一列提供拖拽手柄，松手后同步顺序与收银台预览。
- 同一模板不可重复添加同一支付产品。
- 宽表格的操作列固定在右侧，其他列横向滚动，不得压缩至文字重叠。
- 详情页为只读表达；状态与展示条件分开，空值明确显示“未配置 · 不展示”。
- 页面元素顺序固定为：品牌名称、Logo、主题色、客服电话、邮箱地址、在线客服、常见问题。
- 品牌名称默认“易宝支付”，最多 20 字；为空不展示。

## 输出约束

- Figma：新增页面或状态画板，不覆盖无关原稿；命名清晰并补齐核心原型连线。
- HTML：核心控件必须可操作并经过浏览器验证；全局应用视觉规范中的跨平台系统字体栈。
- 评审：先给按优先级排序的问题，再给可执行修改建议；未获授权不改稿。
- 交付：说明新增或修改位置、验证结果及可访问链接，避免复述过程。

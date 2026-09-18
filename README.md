# AT 收银台运营后台设计 Skill

一套面向 AT 收银台运营后台的 Codex Skill，用于把产品需求、页面截图或现有 Figma 稿转化为一致、可复核、可实现的后台页面与交互。

默认采用品牌蓝 `#1E75FF` 和跨平台系统字体栈：macOS 中文优先苹方，Windows 中文优先微软雅黑，并遵循 Arco Design 的输入、反馈与后台交互习惯。

## 适用场景

- 收银台模板配置：列表、新增、修改、详情与商户级覆盖配置
- 商户支付产品配置：查询、宽表格、固定操作列与横向滚动
- 支付方式配置：新增、编辑、删除、拖拽排序与实时预览
- 复核流程：待复核列表、复核记录、通过、驳回与二次确认
- 页面元素配置：品牌名称、Logo、主题色、辅助色、客服电话、邮箱、在线客服与常见问题
- 设计交付：写入 Figma、补充原型连线或生成可交互 HTML
- 页面评审：检查信息层级、业务完整性、视觉一致性和实现风险

## 核心能力

### 1. 从需求生成完整后台流程

Skill 不只生成单个静态页面，还会补齐与任务相关的默认态、操作态、确认态、错误态和结果态，并确保页面之间的跳转关系完整。

### 2. 固化关键业务规则

- 新增、修改、删除均进入待复核，复核通过后生效。
- 删除操作必须先确认，再提交“删除待复核”。
- 驳回时复核意见必填，最多 100 字；未填写时保留弹窗并显示行内错误。
- 支付方式按列表顺序展示，支持通过拖拽手柄调整顺序。
- 同一模板不可重复添加同一支付产品。
- 宽表格固定右侧操作列，其余内容横向滚动，避免文字重叠。
- 详情页只读展示，空值明确表达为“未配置 · 不展示”。

### 3. 统一页面元素与主题配置

页面元素顺序固定为：

1. 品牌名称
2. Logo
3. 主题色
4. 客服电话
5. 邮箱地址
6. 在线客服
7. 常见问题

品牌名称默认“易宝支付”，最多 20 字，为空时前台不展示。主题色支持固定色板、自定义颜色、历史色值、辅助色，以及预览与恢复默认。

## 安装

在 Codex 中通过 GitHub 仓库安装：

```text
https://github.com/chuhansun81-mm/Check-out
```

也可以直接对 Codex 说：

```text
请安装 GitHub 仓库 chuhansun81-mm/Check-out 中的 Skill。
```

安装后，Skill 名称为：

```text
checkout-operations-admin-design
```

## 使用示例

```text
使用 $checkout-operations-admin-design，根据需求生成收银台模板配置列表、新增页和详情页，并补齐页面交互。
```

```text
使用 $checkout-operations-admin-design，检查这个商户支付产品配置页面，修复宽表格内容重叠，并固定右侧操作列。
```

```text
使用 $checkout-operations-admin-design，把现有页面写入 Figma 新页面，不覆盖原稿，并连接新增、保存、复核和删除流程。
```

```text
使用 $checkout-operations-admin-design，生成可在线预览的 HTML 原型，实现主题色选择、拖拽排序、二次确认和错误提示。
```

## 输出约定

### Figma

- 新增页面或状态画板，不覆盖无关原稿。
- 页面、弹窗和状态命名清晰。
- 补齐关键原型连线。
- 优先复用现有设计系统组件、变量与样式。

### HTML

- 沿用已有项目结构与视觉规范。
- 查询、展开、颜色应用、拖拽、弹窗和预览同步必须真实可操作。
- 完成后通过浏览器验证主要流程。

### 页面评审

- 先列出按优先级排序的问题。
- 再给出可执行的修改建议。
- 未经授权不直接修改设计稿。

## 目录结构

```text
Check-out/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── acceptance-checklist.md
    ├── domain-model.md
    ├── figma-workflow.md
    ├── interaction-spec.md
    ├── page-map.md
    ├── page-patterns.md
    └── visual-spec.md
```

## 参考资料说明

| 文件 | 内容 |
| --- | --- |
| `page-map.md` | 页面地图与完整业务流程 |
| `visual-spec.md` | 导航、栅格、字体、颜色与组件规范 |
| `page-patterns.md` | 列表、表单、详情等页面模式 |
| `interaction-spec.md` | 主题色、拖拽、复核、删除等交互规则 |
| `domain-model.md` | 字段、状态与业务对象定义 |
| `figma-workflow.md` | Figma 写入与原型连接流程 |
| `acceptance-checklist.md` | 交付前验收清单 |

## 设计基线

- 主色：`#1E75FF`
- Web/HTML 字体栈：`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", sans-serif`
- macOS 中文优先：`PingFang SC`（苹方）
- Windows 中文优先：`Microsoft YaHei`（微软雅黑）
- Figma 不支持系统字体栈自动切换：macOS 设计环境优先苹方，Windows 设计环境优先微软雅黑
- 组件交互：参考 Arco Design 后台产品习惯
- 页面风格：清晰、克制、可扫描，优先保证复杂配置场景的信息可读性

## 许可证与使用范围

该仓库用于共享 AT 收银台运营后台的设计方法和 Codex 工作流。使用前请确认业务文档、品牌资产和页面数据符合所在团队的权限与合规要求。

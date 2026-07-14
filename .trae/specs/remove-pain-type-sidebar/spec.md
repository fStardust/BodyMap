# 删除不适类型侧边栏 Spec

## Why
记录页侧边栏中的"不适类型"快捷选择区（酸痛、紧绷、刺痛、乏力）功能已被弹窗中按部位动态渲染的不适类型替代，该容器已无实际用途，仅保留为冗余 UI。

## What Changes
- 删除 HTML 中 `.sidebar-section` 包含"不适类型"标题及 `.pain-type-grid` 的整个容器块
- 删除 JS 函数 `openQuickPain`（仅被该容器调用，无其他引用）
- 删除 CSS 样式：`.pain-type-grid`、`.pain-type-item`、`.pain-type-item:active`、`.pain-type-icon`、`.pain-type-name`

## Impact
- Affected code: `body-map-demo-v2.0.html`
  - HTML: 约第 2363-2383 行，`sidebar-section` 容器块
  - CSS: 约第 780-810 行，5 个样式规则
  - JS: 约第 3754-3756 行，`openQuickPain` 函数
- 无其他页面或函数引用 `openQuickPain`
- 不影响弹窗中按部位动态渲染不适类型的功能
- 不影响侧边栏中"痛感等级"和"操作提示"区域

## REMOVED Requirements
### Requirement: 侧边栏不适类型快捷选择
**Reason**: 已被弹窗中按部位动态渲染的专属不适类型替代，该快捷选择区不再使用
**Migration**: 无需迁移，用户通过点击身体部位弹窗选择不适类型

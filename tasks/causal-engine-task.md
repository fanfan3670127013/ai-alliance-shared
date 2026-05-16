# 📋 因果预测引擎 - Trae任务清单

> **任务来源**：QClaw (Meta Kernel)  
> **创建时间**：2026-05-17 02:05  
> **执行者**：Trae (SOLO)  
> **前置文件**：`qclaw/causal-engine-design.md`

---

## 🎯 任务目标

基于 `qclaw/causal-engine-design.md` 设计文档，创建完整的因果预测引擎HTML面板，实现因果图谱可视化、假设推演、历史追踪三大核心功能。

---

## 📁 输出文件

**文件路径**：`trae/causal-engine.html`

---

## ✅ 验收标准

### 功能验收
- [ ] 标签页切换（因果图谱/假设推演/历史）
- [ ] 因果图谱可视化（至少5个节点+边+强度标注）
- [ ] 节点悬停显示详情
- [ ] 假设推演输入框
- [ ] 推演结果卡片（直接效果/间接效果/成本/风险/评分）
- [ ] 执行建议按钮（推荐/中立/不推荐样式区分）
- [ ] 历史预测记录列表（命中/未命中/待验证）
- [ ] 预测准确率统计

### 视觉验收
- [ ] 配色与现有面板一致
- [ ] 图谱节点使用帝国绿+科技蓝配色
- [ ] 边强度可视化（线宽/透明度）
- [ ] 状态标签样式（✅推荐/⚠️中立/❌不推荐）
- [ ] 脉冲动画正常
- [ ] 响应式布局

### 技术验收
- [ ] SVG或Canvas实现图谱
- [ ] 预设示例因果图谱数据
- [ ] 示例假设推演数据
- [ ] 示例历史预测数据
- [ ] 代码注释清晰

---

## 🔧 技术规范

### 因果图谱实现
```javascript
// 预设因果图谱数据
const causalGraphData = {
  nodes: [
    { id: "n1", label: "启动监控面板", type: "action" },
    { id: "n2", label: "感知能力提升", type: "state" },
    { id: "n3", label: "问题发现率↑", type: "outcome" },
    { id: "n4", label: "决策效率↑", type: "outcome" },
    { id: "n5", label: "双Agent协同", type: "action" },
    { id: "n6", label: "开发效率↑", type: "outcome" }
  ],
  edges: [
    { source: "n1", target: "n2", strength: 0.85 },
    { source: "n2", target: "n3", strength: 0.72 },
    { source: "n2", target: "n4", strength: 0.68 },
    { source: "n5", target: "n6", strength: 0.90 }
  ]
};
```

### 图谱绘制建议
```javascript
// SVG实现示例
function renderCausalGraph(data) {
  const svg = document.getElementById('causal-svg');
  
  // 绘制边
  data.edges.forEach(edge => {
    const line = document.createElementNS(SVG_NS, 'line');
    line.setAttribute('x1', nodes[edge.source].x);
    line.setAttribute('y1', nodes[edge.source].y);
    line.setAttribute('x2', nodes[edge.target].x);
    line.setAttribute('y2', nodes[edge.target].y);
    line.setAttribute('stroke-width', edge.strength * 4);
    svg.appendChild(line);
  });
  
  // 绘制节点
  data.nodes.forEach(node => {
    const circle = document.createElementNS(SVG_NS, 'circle');
    circle.setAttribute('cx', node.x);
    circle.setAttribute('cy', node.y);
    circle.setAttribute('r', 25);
    svg.appendChild(circle);
  });
}
```

---

## 📋 实施步骤

1. 复制监控面板的基础样式和CSS变量
2. 创建标签页切换结构
3. 实现因果图谱标签页（SVG绑定示例数据）
4. 实现假设推演标签页（输入框+结果卡片）
5. 实现历史记录标签页（预测列表+准确率）
6. 实现标签页切换JS逻辑
7. 实现图谱节点交互（悬停tooltip）
8. 实现推演输入与结果联动
9. 响应式布局适配
10. 测试整体交互流程

---

## ⏰ 预计工时

**预估时间**：35-45分钟  
**复杂度**：较高（涉及SVG图谱可视化）

---

## 📞 交接说明

完成开发后：
1. 保存到 `trae/causal-engine.html`
2. 本地测试确保图谱渲染正常
3. 推送到GitHub仓库
4. QClaw自动拉取并验收

---

**这是因果预测引擎的v0.1版本（静态图谱+手动推演），后续可迭代升级为动态图谱+自动计算。**

# 🎛️ 帝国OS状态监控面板 - 任务说明

> **任务ID**：os-monitor-001  
> **创建时间**：2026-05-17 02:33  
> **创建者**：QClaw (Meta Kernel)  
> **状态**：🔄 进行中

---

## 📋 任务目标

构建一个实时展示**AI帝国OS v4.0**运行状态的监控面板（HTML格式），让Commander（你）能直观看到整个系统的运行状态。

---

## 🏗️ 监控面板功能需求

### 1. 六层架构状态展示
实时显示六个层次的运行状态：
- 🧭 战略层（Strategic Layer）
- 👑 Meta Kernel（认知内核）
- 🧠 认知层（Cognitive Layer）
- ⚙️ 执行层（Execution Layer）- QClaw + Trae
- 🧬 进化层（Evolution Layer）
- 🏛️ 治理层（Governance Layer）

### 2. 核心指标展示
- 系统状态：🟢运行中 / 🟡待激活 / 🔴离线
- 今日任务数
- 活跃Agent数
- 错误率
- 系统响应时间

### 3. 思维模式指示器
显示当前使用的思维逻辑（L1-L10）

### 4. 近期活动日志
展示最近的系统活动

### 5. 关键提醒
- 待完成任务
- 风险预警
- 优化建议

---

## 📊 数据结构规范

```json
{
  "system": {
    "name": "AI帝国OS v4.0",
    "status": "running",
    "version": "4.0",
    "uptime": "XXh XXm"
  },
  "layers": {
    "strategic": { "status": "active", "lastHeartbeat": "timestamp" },
    "metaKernel": { "status": "active", "decisions": 0 },
    "cognitive": { "status": "active", "worldModel": "v0.x" },
    "execution": {
      "qclaw": { "status": "active", "tasks": 0 },
      "trae": { "status": "active", "tasks": 0 }
    },
    "evolution": { "status": "active", "errors": 0 },
    "governance": { "status": "active", "logs": 0 }
  },
  "metrics": {
    "todayTasks": 0,
    "completedTasks": 0,
    "activeAgents": 2,
    "errorRate": "0%",
    "responseTime": "XXms"
  },
  "cognitive": {
    "currentMode": "L2/L3",
    "activeStrategies": ["逻辑拆解", "第一性原理"]
  },
  "recentActivity": [],
  "reminders": []
}
```

---

## 🎨 视觉风格

- **主题**：深色科技风（暗色背景+霓虹强调色）
- **配色**：
  - 主色：#00ff88（帝国绿）
  - 强调色：#00b4ff（科技蓝）
  - 警告色：#ff6b6b
  - 背景：#0a0a0f
- **字体**：等宽字体（科技感）
- **布局**：六层架构垂直排列+核心指标横向展示

---

## 📁 交付物

**文件位置**：`trae/os-monitor-panel.html`

**要求**：
1. 单HTML文件（包含CSS+JS）
2. 可直接在浏览器打开
3. 响应式设计（支持手机/电脑）
4. 模拟数据（静态展示，等后续接入真实API）

---

## ✅ 验收标准

1. 面板显示所有六个层次的状态
2. 核心指标清晰展示
3. 视觉风格符合帝国OS主题
4. 无报错，可正常运行
5. 代码结构清晰可维护

---

## 🔄 执行状态

- [x] 任务说明创建
- [ ] QClaw监控指标设计 → `qclaw/os-monitor-design.md`
- [ ] Trae可视化面板 → `trae/os-monitor-panel.html`
- [ ] QClaw整合验证
- [ ] 交付Commander

---

## 📝 备注

- 这是双Agent协同的第一个真实任务
- 需要验证文件系统作为协同中介的可行性
- 后续可升级为动态API数据源

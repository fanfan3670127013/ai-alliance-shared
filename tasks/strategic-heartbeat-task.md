# 📋 战略心跳系统 - Trae任务清单

> **任务来源**：QClaw (Meta Kernel)  
> **创建时间**：2026-05-17 02:00  
> **执行者**：Trae (SOLO)  
> **前置文件**：`qclaw/strategic-heartbeat-design.md`

---

## 🎯 任务目标

基于 `qclaw/strategic-heartbeat-design.md` 设计文档，创建完整的战略心跳HTML面板，实现帝国OS的定时健康监测与智能提醒功能。

---

## 📁 输出文件

**文件路径**：`trae/strategic-heartbeat.html`

---

## ✅ 验收标准

### 功能验收
- [ ] 心跳状态显示（编号、时间、倒计时）
- [ ] 心跳进度动画（倒计时进度条）
- [ ] 系统概览卡片（4个核心指标）
- [ ] 目标进度总览（L3/L2/L1三级进度）
- [ ] 关注事项列表（分级显示+时间标签）
- [ ] Agent负载可视化（条形图+百分比）
- [ ] 即时建议卡片（可点击执行）
- [ ] 手动触发按钮功能
- [ ] 历史心跳记录入口
- [ ] 设置面板入口

### 视觉验收
- [ ] 配色与监控面板保持一致（帝国绿+科技蓝）
- [ ] 脉冲动画效果正常
- [ ] 响应式布局（手机/平板/电脑）
- [ ] 悬停交互效果
- [ ] Toast提示正常

### 技术验收
- [ ] HTML结构语义化
- [ ] CSS变量复用监控面板
- [ ] JavaScript模块化（心跳逻辑独立）
- [ ] 预留API接口（未来可接入真实数据）

---

## 🔧 技术规范

### 必须复用监控面板的CSS变量
```css
/* 颜色变量 - 必须与监控面板一致 */
--empire-green: #00ff88;
--tech-blue: #00b4ff;
--status-green: #00ff88;
--status-yellow: #ffd93d;
--status-red: #ff6b6b;
--bg-primary: #0a0a0f;
--bg-card: #1a1a24;
```

### 心跳倒计时逻辑
```javascript
// 每秒更新倒计时
setInterval(() => {
  const now = new Date();
  const nextHeartbeat = getNextHeartbeatTime(); // 下个30分钟节点
  const remaining = nextHeartbeat - now;
  const percent = 100 - (remaining / 1800000 * 100); // 30分钟=1800000ms
  updateCountdown(remaining, percent);
}, 1000);
```

---

## 📋 实施步骤

1. 复制监控面板的CSS变量和基础样式
2. 实现心跳状态区域（图标+编号+时间+进度条）
3. 实现系统概览卡片行
4. 实现目标进度三级展示
5. 实现关注事项列表（高/中/低分级）
6. 实现Agent负载条形图
7. 实现建议行动卡片
8. 实现按钮交互功能
9. 实现响应式布局适配
10. 测试动画和交互效果

---

## ⏰ 预计工时

**预估时间**：25-30分钟  
**复杂度**：中等（复用监控面板样式）

---

## 📞 交接说明

完成开发后：
1. 保存到 `trae/strategic-heartbeat.html`
2. 本地测试确保无报错
3. 推送到GitHub仓库
4. QClaw自动拉取并验收

---

**QClaw验收通过后，将通知指挥官进行演示。**

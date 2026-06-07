# 悦排 · 智能病例调度工作台 (YuePai / CasePilot)

> 领健（LinkedCare）旗下消费医疗数字化服务平台中，专为正畸方案设计师打造的 **AI 核心驱动智能病例调度工作台**。本仓库包含悦排系统的产品需求文档（PRD）、交互原型、商业方案及用户研究等核心资产。

---

## 📂 项目文件结构

| 文件名 | 类型 | 说明 |
| :--- | :--- | :--- |
| 📄 [README.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/README.md) | Markdown | 项目自述文件（本文档） |
| 📄 [case_workbench_PRD_v2.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/case_workbench_PRD_v2.md) | PRD 文档 | **悦排 · 智能工作台 PRD v2.1**，包含核心算法、AI 提炼规格、三智能体架构及后续迭代路线图 |
| 📄 [yuepai-workbench.html](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-workbench.html) | HTML | **悦排工作台高保真交互式前端原型**，支持四色分区、双视图切换、Inline Drawer、AI 助手面板等核心交互功能演示 |
| 📄 [yuepai-customer-journey-map.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-customer-journey-map.md) | Markdown | 悦排正畸方案设计师的**用户体验旅程图（User Journey Map）**与痛点分析 |
| 📄 [yuepai-prd-ppt.html](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-prd-ppt.html) | HTML | **悦排 PRD 方案演示 PPT**（基于 HTML 格式，支持浏览器直接播放展示） |
| 📄 [yuepai-ppt-script.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-ppt-script.md) | Markdown | 方案演示 PPT 的汇报讲解逐字稿 |
| 📄 [company background.txt](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/company%20background.txt) | Text | 领健（LinkedCare）公司背景介绍与战略定位参考资料 |
| 🖼️ [logo.png](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/logo.png) | Image | 悦排/领健项目 Logo 资产 |

---

## 🌟 核心系统功能设计

针对目前正畸方案设计师面临的**优先级判断难、跳转详情页摩擦高、修改信息断层**等核心痛点，悦排工作台引入了以下三大解决方案：

### 1. 取消 Tab 隔离，引入 AI 动态优先级引擎
* **SLA 风险评分算法**：综合考虑 `剩余时效`、`任务类型权重`、`协作状态` 及 `医生画像`，动态计算病例的紧急程度评分（Risk Score）。
* **四色优先级分区**：
  * 🔴 **Critical（红区）**：立即处理，SLA 严重临期或退回急改病例。
  * 🟡 **Urgent（黄区）**：按序处理，首版设计病例。
  * 🔵 **Pending（蓝区）**：监控状态，等待医生/内审确认。
  * ⚪ **Paused（灰区）**：资料缺失，挂起等待诊所补传。
* **全局看板**：支持多区域叠加筛选及 30 秒倒计时自动更新。

### 2. 黄金字段矩阵与信息密度优化
* 取消多级无效跳转，列表行内“常显”由 AI 自动识别的错颌标签、医生配合度星级、以及**各状态病例的摘要文字**（如退回原因、内审驳回意见或首版设计要点）。
* **信息渐进披露（Hover Card）**：鼠标悬停在异常状态时，300ms 触发 Hover 卡片，快速预览 AI 结构化提炼的修改清单或缺失物料，并支持直接在卡片内一键催办。

### 3. 异常流处理链路的行内化（Inline Drawer）
* 点击“立即修改”可直接在当前行下方展开 **Inline Drawer（操作抽屉）**，无需跳转详情页。
* 抽屉中集成了 **AI 结构化修改清单** 与 **V1 版 vs 医生修改参数的对比矩阵**，支持一键将参数传输给 3D CAD 软件，彻底解决跨软件修改信息断层导致的误改风险。

### 4. 三智能体（Triple-Agent）架构
* 基于 **Hub-and-Spoke 拓扑**，由 `Agent 1 综合信息处理 Hub` 连接 `Agent 2 沟通协作智能体` 与 `Agent 3 图像识别智能体`。
* `Agent 3` 在病例入队前进行 AI 图像预检（CV 质量检测），缺失资料自动挂起并发送补传提醒，大大释放设计师的前期核查耗时。

---

## 🛠️ 如何运行和体验项目

1. **阅读设计文档与 PRD**：
   * 推荐使用支持 Markdown 的阅读器（如 VS Code、Typora 等）打开 [case_workbench_PRD_v2.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/case_workbench_PRD_v2.md) 了解完整的解决方案规格。
2. **体验高保真工作台原型**：
   * 在文件管理器或终端中，直接双击或通过浏览器打开 [yuepai-workbench.html](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-workbench.html)。
   * 该原型完全采用纯 HTML/CSS/JS 编写，包含完整的侧边栏、状态过滤、列表行 Hover、抽屉展开、AI 助手面板折叠等真实前端交互动效，无任何外部框架依赖。
3. **查看 PRD 汇报演示 PPT**：
   * 同样可使用浏览器直接打开 [yuepai-prd-ppt.html](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-prd-ppt.html) 浏览交互式展示幻灯片，同时可配合阅读 [yuepai-ppt-script.md](file:///c:/Users/THC/Desktop/当前工作资料/个人antigravity/linkcare/yuepai-ppt-script.md) 进行讲解。

---

## 🏢 关于 领健 (LinkedCare)

领健成立于 2015 年，总部位于上海，是国内领先的消费医疗数字化服务平台。公司采用 **SaaS+X**（软件+商城+AI+智能制造）商业模式，聚焦于口腔、医美等领域。其隐形正畸矫治器品牌 **“悦见4D”** 拥有国内首个获 NMPA 注册与 FDA/CE 认证的直接 3D 打印技术，已为全国超过 4 万家医疗机构提供数智化闭环解决方案。

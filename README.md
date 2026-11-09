# 📚 Paper & Journal Progress Tracker

> 一个轻量级、零配置、开箱即用的科研论文投稿进度追踪与感兴趣期刊管理系统。采用纯前端架构，支持多轮转投轨迹追踪、JCR/中科院分区管理及本地 JSON 数据持久化。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-Pure%20Vanilla-orange.svg)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue.svg)](https://pages.github.com/)

---

## ✨ 核心特性

- 🚀 **零后端依赖**：纯前端 HTML +原生 JavaScript 实现，无需配置服务器或数据库，双击即可本地运行，完美适配 GitHub Pages 托管。
- 📦 **智能数据加载**：支持**自动检测并加载同目录下的 `papers_data.json`**，也可通过网页端一键导入/导出 JSON 备份文件。
- 🔄 **多轮转投与评审轨迹追踪**：当论文不幸遭遇拒稿并开启新一轮转投时，系统会完整保留前序所有期刊的评审时间线（Round 1, Round 2...），清晰复盘投稿历程。
- 🏢 **全面的期刊库管理**：
  - 涵盖主流学术出版社（IEEE、Elsevier、Springer Nature、Wiley、Taylor & Francis 等）。
  - 分块卡片式网格布局，第一行展示 **JCR 分区、中科院分区、所属出版社**，第二行展示 **OA 属性、双通讯政策**。
- 🔍 **多维检索与筛选**：支持按论文题目、目标期刊、作者、作者位次（第一作者、通讯作者等）以及当前稿件状态进行实时过滤与搜索。

---

## 🛠️ 快速开始

### 方法一：直接本地使用
1. 下载本仓库的 `index.html` 文件。
2. 在同目录下新建一个 `papers_data.json` 作为默认数据文件（可参考仓库中的 `papers_data.json` 范例）。
3. 直接双击 `index.html` 即可在浏览器中愉快使用！

### 方法二：部署到 GitHub Pages (公开分享)
1. Fork 或 Clone 本仓库。
2. 将 `index.html` 和你的 `papers_data.json` 放在仓库根目录下。
3. 进入仓库的 **Settings -> Pages**，将 Source 设置为 `main` 分支根目录，点击 Save。
4. 几秒钟后即可通过 GitHub 提供的链接在线访问你的专属追踪系统！

---

## 📄 `papers_data.json` 数据结构范例

如果你想在仓库中放置默认示例，或使用脚本自动生成数据，可参考以下 JSON 格式：

```json
{
  "papers": [
    {
      "id": "demo_paper_01",
      "title": "Deep Learning Framework",
      "journal": "Nature Machine Intelligence",
      "type": "期刊",
      "status": "Under Review",
      "authorRole": "第一作者",
      "authors": "Zhang, San; Wang, Ling; Chen, Wei*",
      "submitDate": "2026-02-15",
      "notes": "一审中，已分配 3 位审稿专家。",
      "rounds": [
        {
          "roundNum": 1,
          "journal": "IEEE Transactions on Medical Imaging",
          "history": [
            { "id": "h_01", "date": "2026-02-15", "status": "Submitted", "note": "完成初稿提交与格式检查" },
            { "id": "h_02", "date": "2026-02-20", "status": "With Editor", "note": "主编完成初步审查并分配副主编" },
            { "id": "h_03", "date": "2026-03-05", "status": "Under Review", "note": "外审邀请已发出，进入评审期" }
          ]
        }
      ]
    }
  ],
  "targetJournals": [
    {
      "id": "demo_j_01",
      "name": "IEEE Transactions on Multimedia",
      "publisher": "IEEE",
      "jcr": "Q1",
      "cas": "1区",
      "isOA": "混合",
      "allowDualCorr": "允许",
      "notes": "顶级期刊，对算法创新性与临床验证完整性要求极高。"
    }
  ]
}

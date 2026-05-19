# 📌 项目简介

**liduo.github.io** 是一个基于 GitHub Pages 的个人主页项目，既是技术博客/作品集，也是开发者 Liduo（Ihandsomeboy）的线上名片。项目通过纯静态 HTML/CSS/JavaScript 构建，托管在 GitHub Pages 上。

---

## 👤 关于作者

- **角色**：应用开发工程师  
- **关注方向**：LLM 落地产品化、Web 全栈开发、AI 集成系统  
- **GitHub**：[https://github.com/Haze-mode/](https://github.com/Haze-mode/)

---

## 📄 页面组成

| 文件                | 说明                       |
|---------------------|----------------------------|
| `index.html`        | 个人主页，包含个人信息、项目卡片、联系方式 |
| `project-party.html`| 毕业设计项目详情页         |
| `README.md`         | 仓库说明文件               |

---

## 🚀 主要项目

### 1. 基于 GLM-4 的党建智能问答系统

毕业设计项目，核心是 **模型微调（LoRA）+ 知识库检索增强（RAG）** 双机制。

- **技术栈**：`Python` · `Tornado` · `GLM-4-9B-Chat` · `LoRA` · `TF-IDF` · `RAG`

#### 架构（Mermaid 图）

```mermaid
graph TD
    A[用户浏览器] -->|HTTP 请求| B[Tornado Web Server]
    B --> C{RAG 引擎}
    C --> D[知识库检索<br/>TF-IDF]
    C --> E[模型推理<br/>GLM-4 + LoRA]
    D --> E
    E --> F[生成回答]
    F --> B
    B -->|响应| A
```
#### 关键特性

- LoRA 微调，仅训练 0.11% 参数（r=16）  
- PDF/Word/TXT 文档解析 + 段落分块 + TF-IDF 向量检索  
- 双 LRU 缓存（检索缓存 + 回答缓存），命中后响应 < 0.2 秒  
- 多轮对话（保留最近 10 轮）、游客/用户/管理员三级权限  
- Mock 模式，无需 GPU 即可前端联调  

#### 局限与改进方向

- 训练数据规模有限导致过拟合  
- FAISS 因环境依赖未能部署，目前使用 TF-IDF 关键词检索  
- 后续可升级为 BGE + FAISS 稠密向量检索  
- 需补充 Docker 容器化  

### 2. 更多项目开发中

正在探索 Docker 化部署的全栈应用（Django / Vue3 / PostgreSQL），后续会更新。

---

## 🛠️ 技术栈总览

- **前端**：原生 HTML/CSS/JavaScript，响应式布局  
- **托管**：GitHub Pages  
- **后端（项目）**：Tornado 异步框架  
- **AI（项目）**：GLM-4-9B-Chat、LoRA 微调、TF-IDF 检索  

---

## 📬 联系方式

- 邮箱：`your-email@example.com`（待更新）  
- GitHub：[https://github.com/Haze-mode/](https://github.com/Haze-mode/)

---

> 总的来说，这是一个简洁的个人作品集网站，重点展示了一个将 LLM 落地到具体业务场景（党建问答）的完整毕业设计项目，涵盖模型微调、RAG 检索、Web 全栈等工程实践。

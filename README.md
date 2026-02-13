# 💰 家庭财务管理专家

智能识别小票/收据/账单，自动分类，清晰明了。

---

## 📱 在线访问

**网站**: https://ocean-go.github.io/family-finance/

**iPhone 安装**: Safari 打开 → 分享 → 添加到主屏幕

---

## ✨ 功能特点

### 🏠 首页
- 本月收支概览（收入/支出/结余）
- 进度条显示支出占比
- 最近交易记录

### ➕ 智能添加
- 📷 图片上传（小票/收据/账单）
- ✏️ 文字描述输入
- 🤖 AI 智能识别
  - 自动提取金额
  - 自动识别商家
  - 自动判断收支类型
  - 自动建议分类

### 📋 交易记录
- 完整交易列表
- 按日期排序
- 收入/支出清晰标识

### 📊 数据分析
- 分类支出占比（进度条）
- 月度趋势
- 💡 智能建议提醒

---

## 🗂️ 支持分类

| 分类 | 图标 | 说明 |
|------|------|------|
| 餐饮 | 🍔 | 吃饭、外卖、餐厅 |
| 超市 | 🛒 | 日用品、生鲜 |
| 交通 | 🚗 | 打车、公交、地铁 |
| 房租 | 🏠 | 租金、物业 |
| 水电 | ⚡ | 电费、水费、网费 |
| 孩子 | 👶 | 学费、培训 |
| 医疗 | 💊 | 药店、医院 |
| 娱乐 | 🎬 | 电影、游戏 |
| 购物 | 📦 | 服装、礼物 |
| 其他 | 📝 | 其他支出 |
| 收入 | 💰 | 工资、奖金 |

---

## 🔄 版本迭代

### v1.0 - 基础版
- 项目结构搭建
- 基本 UI 框架
- 图片/文字上传
- 数据显示表格
- 基础 AI 识别（关键词匹配）

### v2.0 - 优化版
- 改进 UI 布局，现代深色主题
- 添加加载动画（spinner）
- 添加成功/失败 Toast 提示
- 响应式设计优化
- 分类统计展示
- 交互反馈改进

### v3.0 - 完善版 (当前)
- PWA 支持（可添加到主屏幕）
- 完整智能分类（11个分类）
- 预算超支提醒
- 智能分析建议
- 底部导航栏
- 触摸优化
- Service Worker 准备

---

## 🗄️ 数据存储

### 存储层级 (本地优先)

| 优先级 | 存储 | 说明 |
|--------|------|------|
| 1️⃣ | LocalStorage | 浏览器本地，100%可靠 |
| 2️⃣ | GitHub 仓库 | 云端备份，需配置 Token |

### 配置 GitHub 同步 (可选)

免费！数据存到你自己的 GitHub 仓库：

```javascript
// 在 index.html 中添加 Token
const GITHUB_CONFIG = {
    owner: 'ocean-Go',
    repo: 'family-finance', 
    branch: 'master',
    dataFile: 'data.json',
    token: 'ghp_xxxxxxxxxxxx' // GitHub Personal Access Token
};
```

#### 获取 Token 步骤：

1. 打开 https://github.com/settings/tokens
2. 点击 "Generate new token (classic)"
3. 勾选 `repo` 权限
4. 生成并复制 Token
5. 粘贴到代码中

#### 数据文件

仓库中 `data.json` 文件会自动保存你的财务数据：
- 交易记录
- 最后更新时间

#### 优点
- ✅ 数据存在自己仓库
- ✅ 有版本历史
- ✅ 免费可靠
- ✅ 无需额外服务

---

## 🚀 快速开始

```bash
# 本地运行
cd family-finance
python3 -m http.server 3000
# 浏览器打开 http://localhost:3000
```

---

## 📊 项目结构

```
family-finance/
├── index.html      # 主应用
├── manifest.json   # PWA 配置
├── README.md      # 说明文档
└── .git/         # Git
```

---

## 🔗 相关项目

- [黄金矿工游戏](https://github.com/ocean-Go/gold-miner)
- [Jarvis Dashboard](https://github.com/ocean-Go/jarvis-dashboard)
- [俄罗斯方块](https://github.com/ocean-Go/tetris)

---

## 📄 License

MIT License

---

**Made with ❤️ by Jarvis (MiniMax-M2.5)**

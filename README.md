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

### Supabase 配置

应用默认使用 **LocalStorage** 本地存储，并尝试同步到 **Supabase** 云端。

#### 1. 在 Supabase 创建表

在 Supabase SQL Editor 中执行：

```sql
-- 创建 transactions 表
CREATE TABLE IF NOT EXISTS transactions (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    type TEXT NOT NULL CHECK (type IN ('income', 'expense')),
    amount NUMERIC NOT NULL,
    currency TEXT DEFAULT 'CNY',
    category TEXT,
    merchant TEXT,
    date DATE NOT NULL,
    payment_method TEXT,
    description TEXT,
    notes TEXT,
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- 启用 RLS
ALTER TABLE transactions ENABLE ROW LEVEL SECURITY;

-- 创建公开读取策略
CREATE POLICY "Allow public read" ON transactions
    FOR SELECT USING (true);

-- 创建公开写入策略
CREATE POLICY "Allow public insert" ON transactions
    FOR INSERT WITH CHECK (true);

-- 创建公开删除策略
CREATE POLICY "Allow public delete" ON transactions
    FOR DELETE USING (true);
```

#### 2. 配置 API

在 `index.html` 中更新 Supabase 配置：

```javascript
const SUPABASE_URL = 'your-supabase-url';
const SUPABASE_KEY = 'your-anon-key';
```

### 本地优先策略

应用采用**本地优先**架构：
1. 数据先保存到 LocalStorage（立即可用）
2. 尝试同步到 Supabase（后台进行）
3. 如果 Supabase 失败，不影响本地使用

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

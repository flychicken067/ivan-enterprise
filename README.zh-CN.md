[English](README.md) | **中文**

# ivan-enterprise

面向企业操盘手的 AI 情报简报 —— 用**三张账单**框架过滤所有信息。

**核心原则：跟 operator，不跟 consultant。**
只跟真正做决策的人，不跟评论决策的人。

## 你能得到什么

每周一份发到 Telegram 的决策备忘录：
- 3个来自 operator（CEO/创始人/CTO）的信号，用维护税/聚焦税/版权税过滤
- 1个本周可执行动作
- 1个标注为 ivan-article 候选的话题

## 快速安装

```bash
git clone https://github.com/flychicken067/ivan-enterprise.git ~/.claude/skills/ivan-enterprise
cd ~/.claude/skills/ivan-enterprise/scripts && npm install
```

在 Claude Code 里说：`/ivan-enterprise` 或 "帮我出企业简报"

## 三张账单框架

每条信息都必须通过三张账单过滤：

| 账单 | 含义 | 识别特征 |
|------|------|----------|
| 🔧 维护税 | 维持旧系统运转的持续成本 | 技术债、合规负担、冗余人员 |
| 🎯 聚焦税 | 注意力分散的成本 | 新赛道诱惑、会议文化、KPI 膨胀 |
| ©️ 版权税 | 数据/内容/IP 的隐性成本 | AI 训练数据协议、内容授权、竞业协议 |

## 默认信息来源

**X（只跟 operator，11个账号）：**
Satya Nadella、Aaron Levie、Parker Conrad、Sam Altman、Jensen Huang、Dharmesh Shah、Jason Lemkin、Patrick Collison、Dario Amodei、Brian Chesky、Marc Benioff

**播客（operator 主导，3个）：**
How I Built This、Acquired、My First Million

**一手来源：**
公司工程博客、季报电话会议、CEO 股东信——不跟麦肯锡、不跟 HBR、不跟 Gartner

## ivan-* 技能家族

本技能是 ivan-\* 系列的一部分：
- [ivan-article](https://github.com/flychicken067/ivan-article) — 公众号文章生产流水线
- **ivan-enterprise** — 企业操盘手情报（本技能）
- [ivan-finance](https://github.com/flychicken067/ivan-finance) — 资本决策者情报

灵感来自 [follow-builders](https://github.com/zarazhangrui/follow-builders)（MIT 协议）。

## 开源协议

MIT

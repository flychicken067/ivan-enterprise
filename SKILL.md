---
name: ivan-enterprise
description: >
  AI-powered enterprise intelligence digest for Chinese business leaders.
  Follows operators, not consultants. Every signal filtered through the
  三张账单 (three-bill) framework: 维护税/聚焦税/版权税.
  Trigger: `/ivan-enterprise` or "帮我出企业简报"
version: "1.0"
author: ivan
---

# ivan-enterprise — 企业操盘手情报简报

**核心原则：跟 operator，不跟 consultant**

只跟真正在做决策的人——CEO、创始人、CTO、产品 VP。
不跟顾问、分析师、媒体评论员——不管他们的粉丝量多大。

---

## 触发方式

- `/ivan-enterprise`
- "帮我出企业简报"
- "企业版 digest"
- "老板该看什么"

---

## Phase 0 · 获取数据

运行 fetch 脚本，拉取中央 feed（与 follow-builders 相同机制，不需要 API key）：

```bash
node ~/.claude/skills/ivan-enterprise/scripts/fetch-digest.js
```

如果本地没有 Node 环境，直接告知用户："需要 Node.js，请运行 `npm install` 后重试。"

---

## Phase 1 · 过滤 · 三张账单镜头

拿到原始内容后，**每一条信息都必须通过三张账单过滤**：

| 账单 | 问题 | 信号特征 |
|------|------|----------|
| 维护税 | 这件事是否让企业持续花钱维护旧系统/旧流程？ | 技术债、合规负担、人员冗余 |
| 聚焦税 | 这件事是否让老板注意力分散，偏离核心业务？ | 新赛道诱惑、会议文化、KPI 膨胀 |
| 版权税 | 这件事是否涉及数据/内容/IP 的隐性成本？ | AI 训练数据、内容授权、竞业协议 |

**过滤标准：**
- ⚡ 值得写 → 可以发展为 ivan-article 的完整文章
- ✅ 保留 → 放入简报
- ❌ 跳过 → 来自分析师/顾问/媒体转述，无一手信息

---

## Phase 2 · 生成简报

输出格式：**决策备忘录**（不是新闻摘要，不是资讯汇总）

```
📋 本周企业操盘手情报
━━━━━━━━━━━━━━━━━━━━

🔴 本周3个信号

① [信号标题]
发生了什么：[一句话]
账单类型：[维护税 / 聚焦税 / 版权税]
老板应该问自己：[一个具体问题]
来源：[@handle 或 播客名]

② [信号标题]
...

③ [信号标题]
...

━━━━━━━━━━━━━━━━━━━━
📌 本周1个动作建议

[具体、可执行的一件事，不是"加强AI布局"这类废话]

━━━━━━━━━━━━━━━━━━━━
⚡ 值得深挖（可转 ivan-article）

- [话题] — [一句话说明为什么值得写]
```

**语言**：全中文输出，术语保留英文原词（如 ARR、GTM、CAC）

---

## Phase 3 · 推送

通过 Telegram 发送简报：

```bash
python3 ~/Desktop/AI-Native-Projects/my-first-project/telegram/send.py "$(cat /tmp/ivan-enterprise-digest.md)"
```

---

## 质量检查

在输出简报前，确认：

- [ ] 每条信号都有一手来源（不是转述）
- [ ] 每条信号都标注了账单类型
- [ ] 每条信号都有"老板应该问自己"的问题
- [ ] 动作建议具体可执行（有动词、有对象）
- [ ] 没有来自咨询公司/分析师的内容混入
- [ ] ⚡ 标注了至少1个可转文章的信号

---

## 数据来源

见 `config/default-sources.json`

**X（只跟 operator）：** Satya Nadella, Aaron Levie, Parker Conrad, Sam Altman, Jensen Huang, Dharmesh Shah, Jason Lemkin, Patrick Collison, Dario Amodei, Brian Chesky, Marc Benioff

**播客（operator 主导）：** How I Built This, Acquired, My First Million

**博客（一手来源）：** 公司工程博客、季报电话会议、CEO 股东信

**永远不跟：** McKinsey Insights, HBR, Gartner, 任何"分析师报告"

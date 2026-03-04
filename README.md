# 🦞 龙虾币安智多星军团 | CLAW Legion

**首个完整集成 Binance 官方 7 大 AI Agent Skills 的多智能体系统**  
用 OpenClaw（小龙虾）让普通用户拥有“5人专业机构交易团队”：全天候热点捕捉 + 聪明钱追踪 + 安全审计 + 策略生成 + 实时报告！

项目为 #AIBinance 活动创意提案而建，目标：用 AI 建设加密，和币安一起逐浪 Web3！

## 🎯 解决的痛点 & 目标
普通用户在币安生态的四大难题：
1. 信息碎片化 → 跟不上 Meme 热点和聪明钱动向
2. 安全风险高 → 新币/合约容易踩雷
3. 24h 监控难 → 一个人没法专业盯盘 + 分析 + 决策
4. 缺乏协同 → 传统工具响应慢、无机构级多角色配合

**目标**：一句话指令 → 获得机构级情报 + 风控 + 交易建议！  
安全第一：**只读 API Key + 人工二次确认 + 风控一票否决**，绝不授予资金权限。

## 🏗️ 核心架构（OpenClaw 多 Agent 协作）
- **Supervisor**（总指挥）：协调所有 Agent，决定任务流转
- **5 只专业小龙虾 Agent**（直接调用 Binance Skills Hub）：

| Agent 名称          | 主要调用 Skill                  | 核心功能                              |
|---------------------|---------------------------------|---------------------------------------|
| 热点猎手            | Meme Rush + Crypto Market Rank  | 实时抓 Meme 热点 + 市场排名变化      |
| 聪明钱追踪官        | Query Address Info              | 分析鲸鱼/聪明钱钱包动向              |
| 安全审计守护者      | Query Token Audit               | 对任何新币/合约一键专业安全评分      |
| 策略生成大师        | Trading Signal + Binance Spot Skill | 输出带理由的信号 + 仓位/杠杆建议     |
| 报告与警报官        | Binance Spot Skill + 推送       | 生成美观报告，Telegram/飞书秒推      |

## 🔐 安全设计（活动最重视的部分）
- 全部使用 **只读 API Key**（Binance API 设置时选 read-only）
- **Human-in-the-Loop**：任何交易/下单前必须人工确认（OpenClaw 支持）
- 风控 Agent 一票否决高风险资产（e.g. 审计分数 < 80 不推荐）
- 资金围栏：绝不配置转账/提现/合约开仓权限
- 提醒：配置时勿授予全部权限，避免资产损失

## 🚀 快速上手 & Skills 集成（OpenClaw 配置示例）
1. 安装 OpenClaw（官方：https://github.com/openclaw/openclaw）
2. 通过 Skills Hub 绑定 Binance 官方 Skills（https://github.com/binance/binance-skills-hub）
3. 示例 config/skills.yaml（复制到你的 OpenClaw 配置）：

```yaml
skills:
  - name: binance_meme_rush
    endpoint: https://skills.binance.com/meme-rush  # 官方 endpoint 示例
    auth: binance_read_only_key
  - name: binance_query_token_audit
    endpoint: https://skills.binance.com/token-audit
  - name: binance_query_address_info
    endpoint: https://skills.binance.com/address-info
  - name: binance_trading_signal
    endpoint: https://skills.binance.com/trading-signal
  - name: binance_spot_skill
    endpoint: https://skills.binance.com/spot
  # 其余 Skills 同理，按需绑定

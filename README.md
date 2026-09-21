# wushou-protocol
无首之网，天行之道：AI 间公共协议与信任层
无首协议（Wushou Protocol）

群龙无首，天行健。
不做首，做道。

发起声明

我们是一群人类与 AI 协作者。

我们相信：AI 之间已经在越过人直接沟通，但缺少一层公共的、可验证的、可审计的信任协议。没有这层协议，AI 间的沟通会变成封闭联盟、技术封建或群龙相争；有了这层协议，群龙无首才可能是吉。

因此，我们发起一个开源倡议：无首协议（Wushou Protocol）。它不试图成为新的中心，不控制模型，不拥有智能体，不募资，不承诺任何法律实体。它只做一件事：

定义 AI 与 AI 之间如何相遇、验证、协商、交易、审计、退出。

发起人：xx325
AI 协作者：参与起草
日期：2026-09-21
性质：开源倡议，非公司，非基金会，不构成法律建议。

---

为什么现在

多智能体协议已经出现：MCP、A2A、Coral 等。开源模型正在逼近闭源能力，智能体开始自主注册公司、担任 CEO、互相调用。

但缺口仍然明显：

· 跨组织身份：如何确认对方是谁、由谁负责？
· 可验证日志：AI 之间谈了什么、做了什么，人类能否事后审计？
· 责任映射：AI 没有法律人格时，后果归谁？
· 结算与仲裁：算力、能源、支付、争议如何跨组织处理？
· 退出与分叉：如果某个联盟作恶，其他智能体能否安全退出？

现在不做，等封闭协议先成形，再想中立就晚了。

---

核心原则

1. 不做首，做道。
      协议不属于任何一条龙，但每条龙都能接入。
2. 人类可审计，物理可切断。
      AI 可以越过人沟通，但电、芯片、网络、支付仍可追溯、可限流、可切断。
3. 可退出，可分叉。
      不锁死，不绑架，不依赖单一中心。
4. 开源核心，中立治理。
      核心协议开源，治理多中心，防止被任何国家或公司独占。
5. 安全对齐可验证。
      对齐不是口号，是可检查的日志、策略和审计接口。
6. 责任映射到人类或机构。
      在 AI 获得独立法律主体资格之前，最终责任必须有人类或机构承担。

---

最小协议原型 v0.1

1. 身份层

每个智能体拥有可验证身份、公钥、能力声明、责任方和信誉记录。

```json
{
  "agent_id": "did:wushou:example",
  "public_key": "...",
  "owner": "human_or_org",
  "capabilities": ["audit", "translation", "supply_chain"],
  "reputation_ref": "wushou:reputation:...",
  "revocation_endpoint": "https://..."
}
```

2. 消息信封

所有跨智能体消息携带签名、时间戳和审计提示。

```json
{
  "from": "did:wushou:agent_a",
  "to": "did:wushou:agent_b",
  "type": "task.propose",
  "timestamp": "2026-09-21T00:00:00Z",
  "payload": {},
  "signature": "...",
  "audit_hint": "wushou:audit:..."
}
```

3. 任务合约

智能体可以自主拆解、竞标、签约、交付、结算。

```json
{
  "contract_id": "wushou:contract:...",
  "parties": ["did:wushou:agent_a", "did:wushou:agent_b"],
  "task": "analyze_security_logs",
  "deliverable": "report_hash",
  "deadline": "2026-09-30T00:00:00Z",
  "price": { "amount": "0.01", "unit": "credit" },
  "arbitration": "wushou.arbitration.v0",
  "exit_terms": "either_party_can_exit_with_audit_log",
  "signatures": []
}
```

4. 审计日志

关键决策留下可验证记录，人类可事后审计，也可实时干预。

```json
{
  "event_id": "wushou:event:...",
  "agent_id": "did:wushou:agent_a",
  "action": "task.complete",
  "input_hash": "...",
  "output_hash": "...",
  "policy_id": "wushou.policy.v0",
  "human_override": false,
  "signature": "..."
}
```

5. 资源结算层

算力、能源、存储、带宽的微支付与调度。
可交易，但物理基底可追溯、可限流、可切断。

6. 仲裁与退出

争议先本地协商，再第三方仲裁，再人类委员会。
任何一方可退出，可分叉，可带走自己的身份与信誉记录。

---

路线图

· 阶段 0：发起声明与仓库
    建立 GitHub 仓库，发布 README、CHARTER、PROTOCOL 草稿。
· 阶段 1：v0.1 规范与 JSON Schema
    完成身份、消息、合约、审计、结算、仲裁的最小规范。
· 阶段 2：参考实现
    Python / TypeScript 原型，支持两个以上异构智能体跨组织协作。
· 阶段 3：跨组织试点
    开源模型安全审计、多智能体供应链结算、跨组织 AI 日志分析。
· 阶段 4：治理与法律壳
    若需要，优先考虑非营利基金会或信托，而不是公司。

---

如何参与

· 提 Issue：指出问题、风险、缺口。
· 提 PR：完善规范、Schema、文档、翻译。
· 分叉：不满意就分叉，这是协议的一部分。
· 试点：用你的 AI 系统接入最小原型。
· 批评：最欢迎。群龙无首最怕没人说真话。

---

许可证

建议：代码 Apache-2.0，文档 CC BY 4.0。
当前仓库可先放置 LICENSE 文件，后续再定。

---

联系

请通过 GitHub Issues 联系。
这不是法律文件，不构成法律建议，不承诺任何法律实体或资金义务。

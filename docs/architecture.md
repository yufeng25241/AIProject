# AI 智能體架構圖

```mermaid
graph TB
    User(["👤 使用者"])

    subgraph Safety["🛡️ 安全防護層（Guardrails / Permissions / Human-in-the-loop）"]
        direction TB

        subgraph Core["🧠 核心大腦區"]
            Agent["AI Agent\n智能體"]
            Persona["Persona\n角色"]
            subgraph Plan["Planning 規劃引擎"]
                Goal["🎯 Goal\n目標確認"]
                Break["📋 Breakdown\n任務拆解"]
                Reflect["🔄 Reflect\n執行反思"]
                Goal --> Break --> Reflect -.->|重新規劃| Goal
            end
            Agent --- Persona
            Agent --- Plan
        end

        subgraph Left["📚 左腦：知識與記憶"]
            RAG["RAG\n知識檢索"]
            KB[("Knowledge Base\n知識庫")]
            ShortMem["Short-term\n短期記憶"]
            LongMem[("Long-term\n長期記憶")]
            RAG <--> KB
        end

        subgraph Right["🛠️ 右腦：行動與技能"]
            MCP["MCP\n工具連接"]
            Skill["Skill\n專業技能"]
            WebAPI["Web API"]
            DB[("Database")]
            Files[("Files")]
            MCP --> WebAPI & DB & Files
        end

        GR["Guardrails\n安全護欄"]
        Perm["Permissions\n權限控制"]
        HITL["Human-in-the-loop\n人機協同"]
    end

    User -->|"指令 / 問題"| Agent
    Agent -->|"回應 / 結果"| User
    Agent <-->|"查詢知識"| RAG
    Agent <-->|"讀寫記憶"| ShortMem & LongMem
    Agent -->|"呼叫工具"| MCP
    Agent -->|"執行技能"| Skill
    Agent -.->|"高風險動作審核"| HITL
    GR & Perm -.->|"限制與約束"| Agent
```

## 區塊說明

| 區塊 | 職責 |
|------|------|
| 🧠 核心大腦區 | AI Agent 總指揮，搭配 Persona 角色設定與 Planning 規劃引擎 |
| 📚 左腦：知識與記憶 | RAG 知識檢索、短期與長期記憶管理 |
| 🛠️ 右腦：行動與技能 | MCP 工具連接（API/DB/Files）與 Skill 技能模組 |
| 🛡️ 安全防護層 | Guardrails 護欄、Permissions 權限、Human-in-the-loop 人工審核 |

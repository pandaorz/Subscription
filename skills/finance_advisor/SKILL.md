---
name: Finance Advisor
description: 專為家庭財務管理設計的 AI 技能，包含支出分析、預算預測與訂閱審計功能。
type: skill
---

# Finance Advisor (財務顧問)

此技能旨在增強 AI 對於 `expenses.csv` (流水帳) 與 `subscriptions.md` (預算表) 的分析能力，提供主動式的財務建議。

## 核心能力 (Core Capabilities)

### 1. 支出健康度檢查 (Spending Health Check)
- **觸發時機**: 當使用者詢問「本月支出狀況」、「分析財務」或「有沒有亂花錢」時。
- **執行動作**:
  1. 讀取 `expenses.csv` 當月資料。
  2. 計算 `Total` (總支出)、`Family` (公款) 與 `Personal` (私款) 佔比。
  3. **異常偵測**: 標記單筆超過 $3,000 的非固定支出 (Category 不含 Utility/Telecom)。

### 2. 訂閱一致性審計 (Subscription Audit)
- **觸發時機**: 當使用者詢問「對帳」、「檢查訂閱」或「有沒有漏記」時。
- **執行動作**:
  1. 讀取 `subscriptions.md` 所有 `Status` 為 `⚪` 或 `🟡` 的項目。
  2. 檢查 `expenses.csv` 過去 30 天內是否有對應金額與名稱的記錄。
  3. **產出報告**: 列出「已扣款但未記錄」或「金額不符」的項目。

### 3. 現金流預報 (Cash Flow Forecast)
- **觸發時機**: 當使用者詢問「下個月要繳什麼」、「未來支出」時。
- **執行動作**:
  1. 掃描 `subscriptions.md` 的 `繳費日` 或 `期限`。
  2. 篩選未來 30 天內需繳費的項目（含月繳與即將到期的年繳）。
  3. **預估總額**:這能夠協助使用者預留現金。

### 5. 主動優惠管理 (Proactive Benefit Management)
- **觸發時機**: 每季初期 (1, 4, 7, 10月)、使用者要求「整理優惠」或「怎麼付最划算」。
- **執行動作**:
  1. **外部搜尋**: 使用搜尋工具盤點主流支付（悠遊付、全支付、街口）與手中持卡（玉山、國泰、永豐）的最新活動。
  2. **表格同步**: 將有效優惠填入 `subscriptions.md` 的「2. 信用卡與支付優惠管理」。
  3. **策略媒合**: 針對 `Utility` (生活繳費)、`Child` (學雜費) 提供最佳回饋組合建議。
- **資安範式**: 僅記錄銀行與卡別簡稱（如：玉山 U Bear），嚴禁寫入卡號資訊。

## 互動範式 (Interaction Patterns)

**使用者**: "幫我分析一月的花費"
**AI 回應**:
> ### 📊 1月財務分析報告
> - **總支出**: $12,500
> - **公款 (Family)**: $8,000 (佔 64%)
> - **私款 (Personal)**: $4,500
>
> **⚠️ 注意事項**:
> 1. S82 電費 ($3,000) 較上期增加 20%。
> 2. 尚未記錄 Netflix 扣款，請確認。

---
此技能整合了 *Github Awesome Copilot* 中關於 "Data Analysis", "Financial Planning", 與 "Prompt Engineering for Finance" 的最佳實踐。

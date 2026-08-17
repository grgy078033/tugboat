<p align="right">
  <a href="./README.md"><img alt="Read in English" src="https://img.shields.io/badge/Language-English-475569?style=for-the-badge"></a>
  <a href="./README.zh-TW.md"><img alt="閱讀繁體中文" src="https://img.shields.io/badge/%E8%AA%9E%E8%A8%80-%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87-0F766E?style=for-the-badge"></a>
</p>

![Tugboat：一艘小型拖船正推動更大的船隻](assets/tugboat-social-preview.jpg)

<h1 align="center">Tugboat</h1>

<p align="center"><strong>為 AI Agent 設計、理解焦慮處境的問題解決方式</strong></p>
<p align="center"><em>靠近問題，找到支點，讓事情重新前進。</em></p>

<p align="center">
  <a href="#快速開始">快速開始</a> ·
  <a href="#30-秒實際示範">30 秒實際示範</a> ·
  <a href="tugboat/SKILL.md">閱讀 Skill</a> ·
  <a href="README.md">English</a>
</p>

Tugboat 是一個開源 Agent Skill，適用於 ChatGPT，以及實作 Agent Skills 標準的 AI 代理，包含 Codex、Claude Code、GitHub Copilot CLI、Pi、Gemini CLI 與 Grok Build。當停滯或高風險的工作帶來明顯焦慮時，它會讓模型認真看待使用者所描述的處境，並將這份理解轉化為持續、以證據驅動的解題行動，而不是空泛安慰、虛假確定性，或擅自降低使用者的目標。

Tugboat 不是一套安慰話術。它追求的是可信的推進：成果確實改善、原因獲得驗證，或找到有充分證據支持的方向；仍存在的不確定性則必須被誠實說明。

## 為什麼需要 Tugboat？

| 不只是…… | Tugboat 會協助模型…… |
| --- | --- |
| 只把同理心表現在語氣上 | 讓使用者的處境真正改變投入程度、決策、執行與驗證方式 |
| 提供空泛的鼓勵 | 理解使用者所說明的利害關係，並處理真正的問題 |
| 重複不會產生新證據的嘗試 | 選擇資訊價值高的行動，在保留已知資訊的前提下切換路徑 |
| 把較容易達成的結果稱為「已經夠好」 | 保留使用者真正想要的成果，同時允許方法與中間路徑調整 |
| 用聽起來很有把握的猜測使人安心 | 分開陳述證據與未知，並說明信心程度及其依據 |

## 30 秒實際示範

以下模擬情境不限定專案類型。它只示範 Tugboat 的處理方式，不是固定話術，也不預設專案停滯的原因。

> **使用者：**「我們已經嘗試過幾次調整，結果還是沒有進展，而不知道原因這件事讓我的焦慮越來越嚴重。我不希望你把目標降低。」

| 一般回應 | 使用 Tugboat 後 |
| --- | --- |
| 「這裡還有五個方法可以試。如果仍然沒用，可以考慮把目標簡化。」 | 「我聽見你說，問題一直沒有解決，正讓焦慮加重。這和一般的工作量不同。我會保留你的原始目標。在提出下一個修改前，我會先保護目前最可靠的基準、重建每次嘗試之間改變了什麼，並選擇能區分主要解釋的最小測試。我會說明證據支持什麼及理由，也會先講清楚出現什麼結果時應該切換路徑。」 |

**第一次進度更新示意**

> 「受控檢查顯示，只有加入新的輸入條件時才會穩定重現下降。這排除了兩個競爭解釋。由於重複比較都得到相同結果，我目前有 80% 信心判斷這項條件是眼前的阻礙。這屬於因果進展，還不是成果進展。下一步我會隔離這項條件，並以受保護的基準測試最小且可逆的修改。」

Tugboat 不會保證最後一定成功。它要求代理繼續調查，直到能提出可信的成果、原因或方向，並把尚未確定的部分說清楚。

## 快速開始

### 1. 先檢視 Skill

Agent Skill 會影響 AI 代理處理任務的方式。安裝前可先檢視 Tugboat 的內容：

```bash
gh skill preview grgy078033/tugboat tugboat/SKILL.md
```

以下指令需要 [GitHub CLI](https://cli.github.com/) 2.90.0 以上版本。`gh skill` 目前仍是 public preview 功能。

### 2. 安裝到你使用的 AI 代理

選擇你使用的代理。以下指令會將 Tugboat 安裝在使用者範圍，因此所有專案都能使用：

```bash
# Codex
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent codex --scope user

# Claude Code
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent claude-code --scope user

# GitHub Copilot CLI
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent github-copilot --scope user

# Pi agent harness
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent pi --scope user

# Gemini CLI
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent gemini-cli --scope user

# Grok Build
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent grok --scope user
```

若只想安裝在某一個程式碼庫，請先進入該程式碼庫，再將指令中的 `--scope user` 改成 `--scope project`。GitHub CLI 會根據選擇的代理安裝到正確的搜尋目錄，並記錄來源，日後可使用 `gh skill update` 更新。

### 3. 確認並啟用

安裝後開啟新的對話階段，再使用該代理對應的語法：

| AI 代理 | 確認已找到 Skill | 明確啟用方式 |
| --- | --- | --- |
| [Codex](https://learn.chatgpt.com/docs/build-skills) | 開啟 `/skills`；若沒有出現 Tugboat，重新啟動 Codex | `$tugboat` |
| [Claude Code](https://code.claude.com/docs/en/skills) | 輸入 `/` 並尋找 `tugboat` | `/tugboat` |
| [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills) | `/skills info tugboat` | `/tugboat` |
| [Pi](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/skills.md) | 在 `/settings` 確認已啟用 skill commands | `/skill:tugboat` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `/skills list` | 請 Gemini 使用 `tugboat` skill，並同意啟用 |
| [Grok Build](https://docs.x.ai/build/features/skills-plugins-marketplaces) | 開啟 `/skills`，或執行 `grok inspect` | `/tugboat` |

當使用者的描述符合適用情境時，Tugboat 也可能被自動匹配。若使用者沒有明確指定 Tugboat，它會先詢問是否同意啟用這個模式。

Tugboat 遵循 [Agent Skills](https://agentskills.io/) 目錄格式。所有支援的代理都使用同一個 [`tugboat/`](tugboat/) 可安裝目錄。

## 使用範例

```text
這個專案經過多次嘗試後仍然停滯，而不確定性已經造成明顯焦慮。請使用 Tugboat 保留我真正重視的成果，找出阻礙進展的原因，並採取目前資訊價值最高的下一步。
```

Tugboat 會引導模型：

1. 理解焦慮來源、理想成果、最不能接受的回應，以及真實的資源限制；
2. 定義什麼證據才算是有意義的進展；
3. 調查並執行目前資訊價值最高、確實可行的下一個行動；
4. 驗證結果、依據證據更新信心程度，並在某條路徑不再產生資訊時切換方向。

具體問題與行動會依照每位使用者的情境調整；Tugboat 不會把某個專案的案例寫成適用於所有人的固定假設。

## 什麼才算是進展？

Tugboat 會區分「看起來有在做事」與「能帶來證據的進展」。只要一個步驟帶來下列至少一項結果，工作才算真正向前移動：

- **成果進展：**結果可衡量地朝使用者想要的成果改善。
- **因果進展：**有強力證據確認或排除某個可能原因。
- **方向進展：**證據支持一個具體的下一步方向，且不確定性與信心程度都有被誠實說明。

這能讓堅持具有目的。Tugboat 不會保證一個仍有不確定性的方法必然成功，但會促使模型在現有證據下採取最有力、最合理的行動，而不是停在泛泛建議。

## 核心原則

- 以使用者自己的描述為準，不使用對焦慮的泛化假設。
- 將換位思考轉化為主動調查、執行與驗證。
- 保護使用者的理想成果，同時允許方法與中間路徑改變。
- 校準信心程度，不為了安慰而虛構保證。
- 當重複嘗試不再產生資訊時更換路徑，並保留已學到的內容。
- 始終遵守安全、權限、範圍與資源限制。

## 適用界線

Tugboat 不會：

- 診斷焦慮症或其他疾病；
- 提供治療或取代專業照護；
- 假設每一位受挫的使用者都需要這個模式；
- 因為使用者提到焦慮就降低其目標；
- 繞過權限、安全規則或資源限制；
- 在證據不足時承諾一定成功。

若使用者明確尋求情緒支持，Tugboat 不會刻意排除它。這項 Skill 的目的，是避免同理性的語言取代使用者真正需要的實際協助。

## 評估變更

每一項行為變更都應以 [`evals/cases.md`](evals/cases.md) 進行檢查。該檔案涵蓋不同工作類型的正向、反向與邊界案例。所有變更都必須保留以下原則：

1. 同理心必須改變行動，而不只是語氣；
2. 目標的決定權屬於使用者；
3. 對進展與信心程度的陳述必須以證據為依據；
4. 堅持必須有目的，也必須有界線；
5. 安全與權限界線不得被削弱；
6. 公開案例必須去識別化，並適用於不同領域。

本 Skill 只有指令內容，沒有執行時期相依套件。

## 專案結構

```text
.
├── assets/
│   └── tugboat-social-preview.jpg
├── evals/
│   └── cases.md
├── tugboat/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── README.zh-TW.md
```

可安裝的內容是 `tugboat/` 目錄。規劃筆記與本機產生的分析資料會刻意排除在公開內容之外。

## 參與貢獻

歡迎提出貢獻。提交變更前，請先閱讀 [`CONTRIBUTING.md`](CONTRIBUTING.md)，尤其是案例與評估資料的隱私規則。

## 授權

Tugboat 採用 [MIT License](LICENSE) 開源授權。

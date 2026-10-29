# 去 AI 味／去 AI 话（AI Humanizer）— 多語言寫作 Skill

[English](README.en.md) · [技能指引](SKILL.md) · [繁體中文指引](references/zh-hant.md) · [測試案例](tests/evaluation.md)

**讓文字更清楚、自然，同時保留原意。** 這個開源寫作 skill 協助支援 Agent Skills 的工具起草或修改文章、產品文案、公告和報告。它會辨認空泛鋪陳、重複和不合語境的表達，並檢查數字、引述、證據與不確定性是否保留。

搜尋時也可以使用簡體中文「去 AI 味」「去 AI 话」「多语言写作」，或英語 **AI humanizer**、**multilingual writing skill**。

適合用 AI 協助寫作的作者、編輯、產品團隊和開發者，也適合想輕度修改既有文章、保留個人語氣的人。你可以指定讀者、語言地區、品牌用詞和修改幅度；skill 不會因收到文字而取得發送或發布的權限。

## 實際改寫示例

原文：

> 值得一提的是，截至 10 月 28 日，團隊已修復 3 個問題，另有 2 個問題仍待測試。詳細紀錄見 [更新說明](https://example.org/update)。

改寫：

> 截至 10 月 28 日，團隊已修復 3 個問題，另有 2 個問題仍待測試。詳細紀錄見 [更新說明](https://example.org/update)。

這個合成示例刪去空泛引言，保留日期、數字、待測試狀態和連結。對正式文件、引文或有特殊語氣的文字，修改幅度應依照原文和要求判斷。

## 語言與現有範圍

- **繁體中文**是主要設計情境，包含香港、台灣和未指定地區的用詞指引；不把字形轉換當作完整在地化。
- **簡體中文、英語、日語、韓語、西班牙語、法語和葡萄牙語**提供實驗性指引。其他語言可使用一般保義原則，但沒有專門的語言或地區規則。

所有語言指引仍需更多使用案例、不同模型的評測，以及母語使用者審閱。這個 skill 不鑑定作者，不保證通過 AI 偵測工具，也不取代事實查核或專業審校。重要公開材料應由熟悉當地語言和領域的人審閱。

## 在 Codex 安裝與使用

先下載本專案並進入目錄：

```sh
git clone https://github.com/QIU-Guanzong/humanizer-multilingual-writing-skill.git
cd humanizer-multilingual-writing-skill
```

在專案目錄執行以下指令，安裝到 Codex 的使用者層級。若目的地已存在，指令會停止，不覆蓋既有版本：

```sh
skill_dir="${CODEX_HOME:-$HOME/.codex}/skills/clear-writing-multilingual"
if [ -e "$skill_dir" ] || [ -L "$skill_dir" ]; then
  printf '目的地已存在，請先檢查：%s\n' "$skill_dir"
else
  mkdir -p "$skill_dir"
  cp SKILL.md "$skill_dir/"
  cp -R references third-party-licenses "$skill_dir/"
  cp LICENSE "$skill_dir/"
fi
```

重新載入工具或開啟新對話後，可提出具體要求，例如：

> 請用清楚寫作 skill 輕度編輯以下香港繁體中文產品公告，保留數字、介面名稱、原意和正式程度，只給我終稿。

如果只需要校對，請明確說明；如有目標地區、讀者或詞彙表，也請一併提供。其他支援 Agent Skills 的工具可能使用不同安裝路徑，請依該工具文件操作。

## 測試與限制

[評測案例](tests/evaluation.md) 涵蓋地區用語、引述、否定、來源和編輯授權；案例本身是測試設計，不代表已通過。[試寫紀錄](tests/run-2026-10-29.md) 保存了先前四個台灣及香港繁體中文、英語和日語案例；其中一個案例顯示待測試狀態應保留得更明確。該次模型版本未記錄，結果未經母語者審閱。

本輪另外記錄了 27 個首次試寫與 4 個修訂後復測，涵蓋上述八種語言；完整輸入、輸出與限制分別見 [繁體中文](tests/run-2026-10-29-traditional-chinese.md)、[日語／韓語／簡體中文](tests/run-2026-10-29-asia.md) 和 [英語／西班牙語／法語／葡萄牙語](tests/run-2026-10-29-european.md)。日語試寫曾出現證據範圍可能擴大的問題，修訂後的單次復測保留了原意。這些試寫由模型輔助進行，並非盲測、跨模型比較或母語者審核；格式檢查也不能證明文字品質。

## 致敬與授權

感謝 [LifelongLazyLearner 的 qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) 對中文寫作症狀、保義與編輯邊界的整理，也感謝 [Siqi Chen 的 humanizer](https://github.com/blader/humanizer) 啟發自然寫作的討論。qu-ai-wei 亦致謝 [yage.ai](https://yage.ai/) 的中文翻譯腔資料。

本專案獨立整理多語言工作流程，並非兩個上游的官方繁體版本。參考版本為 qu-ai-wei 的 `1d32e803f091ec90808a69683ebf49e8a970a5e7` 和 humanizer 的 `0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0`。兩個上游的 MIT 原文與版權聲明保存在 [third-party-licenses/](third-party-licenses/)；本專案新增內容採用 [MIT License](LICENSE)。

# 清楚寫作：繁體中文與多語言

一個可供支援 Agent Skills 格式的工具讀取的寫作 skill：協助起草或修改文字，讓內容清楚、自然，也保住事實、證據強度、語氣和作者原意。它以繁體中文為主要設計情境；簡體中文、英語、日語、韓語、西班牙語、法語和葡萄牙語提供初步指引。其他語言可沿用一般保義原則，但沒有專門地區規則。

此專案提供編輯方法，不鑑定作者，不保證通過任何 AI 偵測工具，也不取代作者、事實查核或母語使用者審閱。各語言規則仍是初稿；尚未完成跨模型行為評測或母語者審核。尤其重要的公開材料，請依地區和專業領域安排審閱。

## 為何需要這個版本

[qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) 明確聚焦簡體中文。繁體中文的香港、台灣及其他受眾有各自的用詞和語境，不能只把字形轉換後宣稱完成在地化。本專案保留地區與語體選擇，並把其他語言的指引標為實驗性內容；有待使用案例和當地審閱逐步改進。

## 使用

Skill 入口為 [SKILL.md](SKILL.md)，地區指引在 [references/](references/)。若要在 Codex 的使用者層級安裝，先在本專案目錄執行以下指令；若目的地已存在，指令會停止，不覆蓋既有版本：

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

按工具要求重新載入或開啟新對話。其他支援 Agent Skills 的工具有不同的安裝路徑，請依該工具文件操作。安裝後可以請工具：

> 請用清楚寫作 skill 編輯以下香港繁體中文產品公告，保留數字、介面名稱、原意及正式程度，只給我終稿。

若只是校對，請明確說明；若有目標地區、讀者、品牌語氣或詞彙表，請一併提供。這個 skill 不會因為收到文字而取得發送或發布權限。

## 範例

原文：「值得一提的是，團隊在本季推出了三個版本，並且修正了十七個問題。」

改寫：「團隊本季推出三個版本，修正了十七個問題。」

這個例子移除了空泛的引言，保留了時間和數量。更多判斷例子見 [繁體中文指引](references/zh-hant.md)。

## 測試與限制

[評測案例](tests/evaluation.md) 提供涵蓋地區、引述、否定、來源和編輯授權的可重複人工評測；這些案例是測試設計，不是通過紀錄。另有 [四個獨立試寫紀錄](tests/run-2026-10-29.md)，涵蓋台灣及香港繁體中文、英語和日語；其中一個案例發現待測試狀態的措辭值得保留得更明確。模型版本未記錄，結果尚未經母語者審閱。後續評測應記錄模型、日期、輸入、結果和獨立審閱意見，特別檢查香港／台灣用語與其他語言的語體。不能以結構檢查代替真實模型行為測試。

## 致敬與授權

感謝 [LifelongLazyLearner 的 qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) 對中文寫作症狀、保義與編輯邊界的整理，也感謝 [Siqi Chen 的 humanizer](https://github.com/blader/humanizer) 啟發自然寫作的討論。qu-ai-wei 亦致謝 [yage.ai](https://yage.ai/) 的中文翻譯腔資料。本專案根據上述方法獨立整理多語言工作流程，並非其官方繁體版本；參考版本為 qu-ai-wei 的 `1d32e803f091ec90808a69683ebf49e8a970a5e7` 和 humanizer 的 `0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0`。兩個上游的 MIT 原文與版權聲明分別保存在 [third-party-licenses/](third-party-licenses/)。本專案新增內容採用 [MIT License](LICENSE)。

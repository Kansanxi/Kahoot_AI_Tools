# 🎓 Kahoot AI 自動答題系統（含 Web UI）

這是一個可以 **自動回答 Kahoot 測驗** 的本地專案，結合 LLM（如 Ollama/llama3）來分析題目並作答，並透過簡約 Web UI 顯示目前狀態與歷史答題紀錄 ✨

---

## 🧠 功能特色

- ✅ 自動連接 Kahoot PIN 並答題
- 💡 使用 AI 模型（預設：Ollama 的 Llama3）分析選項並作答
- 📝 顯示目前題目、選項、AI 選擇、難度估算
- 📜 顯示歷史答題紀錄（題目、答案、狀態、難度）
- 📷 顯示圖片型題目（若有）

---

## 🚀 使用教學

### 1️⃣ 安裝依賴

請先安裝 Python 套件：

```bash
pip install flask kahoot.py ollama

並確保你本地已安裝好 Ollama 並啟動 Llama3 模型：

```bash
ollama run llama3

2️⃣ 執行專案
python main.py

3️⃣ 使用說明
預設會連線到 Kahoot 測驗 PIN 123456，你可在 main.py 自行更改：
threading.Thread(target=lambda: kahoot_handler.run_bot(pin=123456, nickname="OllamaBot")).start()

啟動後，請打開瀏覽器進入：
http://localhost:5000

即可看到：

目前題目 + AI 選擇
是否成功匹配正確選項
題目難度估算
答題歷史紀錄列表

---

🛠 FAQ

📸 Q: 題目是圖片怎麼辦？
A: 目前會顯示圖片連結，但 AI 不會讀圖。僅支援文字分析。

🔊 Q: 可以有聲音提示嗎？
A: 預設移除 playsound，避免安裝問題。如需開啟聲音功能，可加入音效程式碼並安裝聲音套件。

🤖 Q: AI 模型可以換嗎？
A: 是的！預設使用本地 Llama3。你也可以自行改成：

Claude（透過 API）
ChatGPT（需要 OpenAI API Key）
其他任意模型（只要有 chat 接口）


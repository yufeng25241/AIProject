# 範例專案 Demo

簡介
- 這是一個最小化的專案骨架，用於示範 Demo、文件與推上 GitHub 的流程。

快速啟動（Windows / 跨平台）

需求：瀏覽器、選用 Python 3（用來啟動本地靜態伺服器，可選）。

本地查看 Demo（方式一：直接開啟）
1. 在檔案總管中打開 `demo/index.html`，或用瀏覽器開啟該檔案。

本地查看 Demo（方式二：啟動簡單 HTTP 伺服器）
```bash
# 在專案根目錄執行（需要 Python 3）
python -m http.server 8000
# 然後在瀏覽器開啟： http://localhost:8000/demo/index.html
```

初始化 git 並推上 GitHub（替換 USERNAME/REPO）
```bash
git init
git add .
git commit -m "chore: initial scaffold"
git branch -M main
git remote add origin git@github.com:USERNAME/REPO.git
git push -u origin main
```

授權
- 預設使用 MIT 授權（可在 `LICENSE` 中修改）。

檔案結構（重點）
- `demo/`：示範的靜態頁面（`index.html`）。
- `docs/index.md`：專案說明與文件首頁。
- `README.md`：快速啟動與說明（本檔）。

## 專案架構圖

以下為本專案的架構示意圖（將顯示 `assets/architecture.png`）：

![Architecture Diagram](docs/screenshots/architecture.png)

若您已將圖檔上傳為 `assets/architecture.png`，此處會直接顯示；否則請將您剛剛上傳的圖片存為該檔名，或允許我替您把附件加入至該路徑。

接下來
- 如果您要我直接在當前目錄初始化 git、建立遠端並推上 GitHub，請提供您的 GitHub 使用者名稱與欲建立的 repo 名稱，或回覆「讓你選」。
# ☕ Corvallis Coffee Map

> 探索 Corvallis 最棒的咖啡店！一個互動式的咖啡店地圖，讓你輕鬆找到符合你心情的完美咖啡廳。

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Updated](https://img.shields.io/badge/updated-Nov%202025-orange.svg)

## 📋 目錄

- [功能特色](#-功能特色)
- [使用方式](#-使用方式)
- [新增咖啡店](#-新增咖啡店)
- [技術架構](#-技術架構)
- [咖啡店分類](#-咖啡店分類)
- [部署指南](#-部署指南)
- [資料管理](#-資料管理)
- [常見問題](#-常見問題)
- [貢獻指南](#-貢獻指南)
- [授權條款](#-授權條款)

---

## ✨ 功能特色

### 地圖功能
- 🗺️ **互動式地圖**：基於 Leaflet.js 的高效能地圖介面
- 📍 **自訂標記**：精美的淚滴狀標記，附帶類別專屬顏色和圖示
- 🎯 **智慧篩選**：按照咖啡店類別快速篩選（氣氛美感、讀書工作、咖啡行家、溫馨聚會）
- 🔍 **自動聚焦**：點擊標記自動平移並開啟詳細資訊
- 📱 **響應式設計**：完美適配桌面、平板、手機裝置

### 新功能（v2.0）
- ➕ **使用者新增功能**：任何人都可以透過表單新增咖啡店
- 💾 **本地儲存**：使用 localStorage 持久化使用者新增的資料
- ✅ **表單驗證**：智慧驗證確保資料正確性（座標範圍、必填欄位等）
- 🎨 **動態標籤**：可動態新增多個咖啡店特色標籤
- 🌓 **暗色模式支援**：自動適應系統主題偏好

### 使用者體驗
- ⚡ **平滑動畫**：標記落下動畫、視窗切換動畫
- ⌨️ **鍵盤快捷鍵**：按 `Esc` 關閉表單視窗
- 🎭 **Loading 動畫**：優雅的載入畫面
- 🔢 **即時計數**：顯示每個類別的咖啡店數量

---

## 🚀 使用方式

### 快速開始

1. **開啟網頁**
   ```
   在瀏覽器中開啟 index.html
   ```

2. **探索咖啡店**
   - 點擊右上角的類別按鈕來篩選咖啡店
   - 點擊地圖上的標記查看詳細資訊
   - 點擊 "在 Google Maps 中開啟" 導航到該地點

3. **新增咖啡店**
   - 點擊左下角的 ➕ 浮動按鈕
   - 填寫表單資訊
   - 提交後立即在地圖上看到新增的地點

### 瀏覽器要求
- Chrome 90+ / Firefox 88+ / Safari 14+ / Edge 90+
- 需啟用 JavaScript
- 建議啟用 localStorage（用於儲存使用者新增的資料）

---

## ➕ 新增咖啡店

### 操作步驟

1. **點擊新增按鈕**
   - 找到左下角的圓形 ➕ 按鈕（手機版在底部中央）
   - 點擊後會開啟表單視窗

2. **填寫基本資訊**
   ```
   必填欄位：
   - 咖啡店名稱：例如 "Greenhouse Coffee + Plants"
   - 類別：選擇最符合的分類
   - 緯度/經度：從 Google Maps 取得座標
   - 圖示名稱：Font Awesome 圖示（不含 fa-）
   - 詳細描述：描述咖啡店的特色、氛圍
   ```

3. **新增特色標籤**
   - 使用表情符號開頭，例如：
     - 📸 適合拍照
     - 💻 插座多
     - ☕ 手沖咖啡
   - 可點擊「新增標籤」按鈕增加更多標籤

4. **提交表單**
   - 檢查資料無誤後點擊「提交」
   - 系統會自動驗證並新增到地圖上
   - 地圖會自動聚焦到新增的地點

### 如何取得座標

**方法一：Google Maps（桌面版）**
1. 在 Google Maps 上找到咖啡店
2. 右鍵點擊地點
3. 座標會顯示在最上方（格式：44.5643, -123.2614）
4. 點擊座標複製

**方法二：Google Maps（手機版）**
1. 長按地圖上的位置
2. 底部會出現座標資訊
3. 點擊座標複製

### 圖示選擇指南

常用的 Font Awesome 圖示名稱（輸入時不含 `fa-`）：

| 圖示名稱 | 適用情境 |
|---------|---------|
| `leaf`, `seedling` | 綠色、植物主題咖啡店 |
| `coffee`, `mug-hot` | 一般咖啡店 |
| `book`, `laptop` | 適合讀書工作的咖啡店 |
| `music`, `guitar` | 有現場音樂的咖啡店 |
| `users`, `heart` | 社區型、聚會咖啡店 |
| `bread-slice`, `croissant` | 強調麵包甜點的咖啡店 |
| `glasses` | 咖啡行家、專業烘焙 |

完整圖示列表：[Font Awesome Icons](https://fontawesome.com/v6/icons)

---

## 🛠️ 技術架構

### 核心技術

```
前端框架：無（Vanilla JavaScript）
地圖引擎：Leaflet.js 1.9.4
圖示庫：Font Awesome 6.0.0
地圖圖層：CartoDB Voyager
資料儲存：localStorage API
```

### 檔案結構

```
corvallis-coffee-map/
├── index.html          # 單一檔案應用（包含 HTML/CSS/JS）
├── README.md           # 本文件
└── .git/               # Git 版本控制
```

### 資料流程

```
使用者輸入表單
    ↓
表單驗證
    ↓
建立咖啡店物件
    ↓
儲存到 localStorage
    ↓
合併至 places 陣列
    ↓
重新渲染地圖標記
    ↓
自動聚焦至新地點
```

### localStorage 結構

```javascript
{
  "userCoffeeShops": [
    {
      "id": 1700000000000,
      "name": "Example Coffee",
      "category": "aesthetic",
      "lat": 44.5643,
      "lng": -123.2614,
      "icon": "leaf",
      "desc": "描述...",
      "features": ["📸 適合拍照", "☕ 手沖咖啡"],
      "link": "https://maps.google.com/..."
    }
  ]
}
```

---

## 🏷️ 咖啡店分類

### 氣氛美感 (Aesthetic)
**圖示**：🍃 綠色
**適合**：拍照打卡、享受美好環境
**特色**：採光佳、裝潢優美、植物裝飾

**預設店家**：
- Greenhouse Coffee + Plants
- Futura Coffee Roasters

---

### 讀書工作 (Study)
**圖示**：💻 橙色
**適合**：讀書、工作、趕論文
**特色**：插座多、空間寬敞、安靜環境

**預設店家**：
- Interzone
- Coffee Culture (Kings)

---

### 咖啡行家 (Nerd)
**圖示**：👓 紫色
**適合**：品味精品咖啡、購買咖啡豆
**特色**：專業烘焙、手沖咖啡、香氣四溢

**預設店家**：
- Oregon Coffee & Tea

---

### 溫馨聚會 (Community)
**圖示**：👥 紅色
**適合**：朋友聚會、社區活動
**特色**：沙發區、現場音樂、藝術展覽

**預設店家**：
- Imagine Coffee Co.
- Bodhi Cafe & Bakery

---

## 🚀 部署指南

### 靜態託管平台

#### GitHub Pages
```bash
# 1. 推送到 GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin <your-repo-url>
git push -u origin main

# 2. 啟用 GitHub Pages
# Settings → Pages → Source: main branch → Save
```

訪問網址：`https://<username>.github.io/<repo-name>/`

#### Netlify
```bash
# 方法一：拖放部署
# 直接將專案資料夾拖放到 app.netlify.com/drop

# 方法二：CLI 部署
npm install -g netlify-cli
netlify deploy --prod
```

#### Vercel
```bash
npm install -g vercel
vercel --prod
```

### 本地開發

```bash
# 使用 Python 3
python3 -m http.server 8000

# 使用 Node.js
npx http-server

# 使用 PHP
php -S localhost:8000
```

訪問：`http://localhost:8000`

---

## 💾 資料管理

### 查看使用者新增的資料

在瀏覽器的開發者工具中執行：

```javascript
// 查看所有使用者新增的咖啡店
console.log(JSON.parse(localStorage.getItem('userCoffeeShops')));

// 查看合併後的所有咖啡店
console.log(places);
```

### 備份資料

```javascript
// 匯出為 JSON
const data = localStorage.getItem('userCoffeeShops');
const blob = new Blob([data], { type: 'application/json' });
const url = URL.createObjectURL(blob);
const a = document.createElement('a');
a.href = url;
a.download = 'coffee-shops-backup.json';
a.click();
```

### 還原資料

```javascript
// 從 JSON 檔案還原
const fileInput = document.createElement('input');
fileInput.type = 'file';
fileInput.accept = 'application/json';
fileInput.onchange = e => {
  const file = e.target.files[0];
  const reader = new FileReader();
  reader.onload = event => {
    localStorage.setItem('userCoffeeShops', event.target.result);
    location.reload();
  };
  reader.readAsText(file);
};
fileInput.click();
```

### 清除所有使用者資料

```javascript
// 清除所有使用者新增的咖啡店
localStorage.removeItem('userCoffeeShops');
location.reload();
```

---

## ❓ 常見問題

### Q: 我新增的咖啡店會永久保存嗎？
**A:** 資料儲存在瀏覽器的 localStorage 中，只要不清除瀏覽器資料就會一直保留。但建議定期備份重要資料。

### Q: 為什麼我在另一台電腦看不到我新增的咖啡店？
**A:** localStorage 是本地儲存，資料只存在於當前裝置和瀏覽器中。如需跨裝置同步，需要使用雲端資料庫。

### Q: 可以編輯或刪除已新增的咖啡店嗎？
**A:** 目前版本僅支援新增功能。如需編輯或刪除，可透過瀏覽器開發者工具手動修改 localStorage。

### Q: 座標輸入錯誤怎麼辦？
**A:** 系統會驗證座標是否在 Corvallis 區域內（緯度 44-45，經度 -124 到 -122）。如果超出範圍會提示確認。

### Q: 支援哪些瀏覽器？
**A:** 支援所有現代瀏覽器（Chrome, Firefox, Safari, Edge）。IE 11 及更早版本不支援。

### Q: 如何取得 Google Maps 連結？
**A:** 在 Google Maps 中找到地點 → 點擊「分享」→ 複製連結。

### Q: 可以離線使用嗎？
**A:** 首次載入後可離線瀏覽已載入的內容，但地圖圖層需要網路連線。

---

## 🤝 貢獻指南

歡迎貢獻新功能或改進！

### 建議的改進方向

- [ ] **編輯功能**：允許使用者編輯已新增的咖啡店
- [ ] **刪除功能**：允許使用者刪除咖啡店
- [ ] **資料匯出**：匯出為 CSV 或 JSON 格式
- [ ] **圖片上傳**：為咖啡店新增照片
- [ ] **評分系統**：允許使用者評分和評論
- [ ] **搜尋功能**：按名稱或特色搜尋咖啡店
- [ ] **後端整合**：連接資料庫實現跨裝置同步
- [ ] **使用者認證**：登入系統和個人收藏
- [ ] **推薦算法**：基於偏好推薦咖啡店
- [ ] **社群功能**：使用者間的互動和分享

### 如何貢獻

1. Fork 此專案
2. 建立功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交變更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

---

## 📄 授權條款

MIT License

Copyright (c) 2025 Corvallis Coffee Map

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## 🙏 致謝

- [Leaflet.js](https://leafletjs.com/) - 開源地圖庫
- [Font Awesome](https://fontawesome.com/) - 圖示庫
- [CartoDB](https://carto.com/) - 地圖圖層提供
- Corvallis 咖啡愛好者社群

---

## 📧 聯絡方式

如有問題或建議，歡迎透過以下方式聯絡：

- 開啟 GitHub Issue
- Email: your-email@example.com
- Twitter: @YourHandle

---

**最後更新：2025 年 11 月 18 日**

☕ 享受你的咖啡時光！

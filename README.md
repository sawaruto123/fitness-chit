# 健身單 · Daily Training Chit

個人日常健身追蹤工具，採用香港地鐵車票風格設計，透過「蓋章」方式記錄每日訓練、蛋白質攝取、體重與睡眠習慣。

簡單、儀式感強，且支援雲端自動同步，適合長期使用。

## 功能特色

- **訓練循環**：Push → Pull → Legs 三天輪替，自動推進
- **休息計時器**：組間休息計時，支援快速切換預設時間
- **蛋白質追蹤**：快速新增 + 手動輸入，目標 150–180g
- **體重記錄**：每日記錄 + 自動計算變化趨勢
- **睡眠打卡**：睡前「收機再瞓」連續紀錄
- **7 天摘要**：訓練次數、蛋白質平均、體重變化、趨勢圖
- **Office Mode**：低調備忘錄模式，適合在公司或學校使用
- **PWA 安裝**：可安裝到手機主畫面，離線可用
- **雲端自動同步**：使用 Supabase 背景同步，換手機也能還原資料
- **資料備份**：一鍵匯出 / 匯入 JSON

## 使用方式

1. 開啟 App 後查看今日應進行的訓練項目（Push / Pull / Legs）
2. 訓練時可使用內建休息計時器
3. 完成後點擊「STAMP TODAY」蓋章
4. 訓練後補充蛋白質並記錄
5. 睡前打勾「收機再瞓」
6. 可隨時查看 7 天摘要了解進度

## 部署方式

本專案為純靜態網頁，可輕鬆部署至 Vercel、Netlify 等平台。

### 使用 Vercel + GitHub 部署（推薦）

1. 將專案推送到 GitHub
2. 在 [Vercel](https://vercel.com) 連接該 Repository
3. 部署完成後即可獲得網址
4. 在 Android Chrome 開啟後可安裝為 PWA

## Supabase 雲端同步設定

本專案支援使用 Supabase 進行自動背景同步。

### 設定步驟：

1. 在 Supabase 建立新專案
2. 建立 `fitness_chits` 資料表（執行下方 SQL）
3. 在 `index.html` 中填入 `SUPABASE_URL` 與 `Publishable key`
4. 重新部署即可啟用自動同步

```sql
create table if not exists fitness_chits (
  user_id text primary key,
  updated_at timestamptz default now(),
  data jsonb
);

alter table fitness_chits enable row level security;

create policy "Allow public access" 
on fitness_chits for all 
using (true) with check (true);

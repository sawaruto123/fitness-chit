<div align="center">

# 🎫 健身單 · Daily Training Chit

**個人日常健身追蹤工具，採用香港復古車票風格設計**
*A personal daily fitness tracker with a retro Hong Kong MTR-ticket aesthetic*

透過「蓋章」方式記錄每日訓練、蛋白質攝取、體重與睡眠習慣 — 簡單、儀式感強，且支援雲端自動同步。
*Stamp your way through workouts, protein intake, bodyweight, and wind-down habits—simple, satisfying, and seamlessly synced.*

![Static Site](https://img.shields.io/badge/type-static%20site-8A9A5B?style=flat-square)
![PWA](https://img.shields.io/badge/PWA-installable-3E5C76?style=flat-square)
![Sync](https://img.shields.io/badge/sync-Supabase-1E293B?style=flat-square)
![Login](https://img.shields.io/badge/login-not%20required-B23A48?style=flat-square)

</div>

<br>

## 📋 目錄 · Contents

* [✨ 功能特色 · Features](#-功能特色--features)
* [📱 使用方式 · How to Use](#-使用方式--how-to-use)
* [🚀 部署方式 · Deployment](#-部署方式--deployment)
* [☁️ Supabase 雲端同步設定 · Supabase Setup](#️-supabase-雲端同步設定--supabase-setup)

---

## ✨ 功能特色 · Features

| 🌟 核心功能 · Core Features | 💡 詳細說明 · Description |
| :--- | :--- |
| **🔁 彈性訓練循環**<br>*Flexible PPL Rotation* | Push → Pull → Legs 三天輪替，自動推進；跳過一天也只需接續下一個循環。<br>*Auto-advancing cycle that picks up right where you left off.* |
| **🆘 應急訓練打卡**<br>*Emergency Stamp* | 狀態極差時可用 15 分鐘低強度選項蓋上「應急」章，維持習慣而不產生罪惡感。<br>*A 15-minute low-intensity option for bad days, keeping the habit guilt-free.* |
| **📊 動態課表與紀錄**<br>*Dynamic Training Log* | 根據當日輪替自動顯示對應動作，支援記錄重量與次數（附護腕/受傷保護提示）。<br>*Displays today's exercises with weight/rep logging and injury prevention tips.* |
| **⏱️ 休息計時器**<br>*Rest Timer* | 組間休息倒數，快速切換 60s / 90s / 120s / 180s。<br>*Between-set countdown with quick presets.* |
| **🥤 蛋白質追蹤**<br>*Protein Tracker* | 快速新增按鈕（Shake、Meal、Snack）＋手動輸入，每日目標 150–180g，附進度條。<br>*Quick-add buttons + manual entry with a 150–180g daily target and progress bar.* |
| **⚖️ 體重記錄**<br>*Bodyweight Log* | 每日記錄並自動顯示與前次的變化趨勢。<br>*Daily entry with an automatic trend comparison against your last record.* |
| **🌙 狀態與睡眠打卡**<br>*Wind-Down Tracker* | 收機再瞓連續紀錄 · 訓前 6 小時無咖啡因 · 睡前/訓練後 10 分鐘冷卻。<br>*Phone-away streak, pre-workout caffeine cutoff, and cooldown tracking.* |
| **📈 7 天摘要**<br>*7-Day Summary* | 訓練次數、睡眠達標數、蛋白質平均值與體重變化，一目了然。<br>*Overview of workouts, sleep consistency, avg. protein, and weight change.* |
| **🕶️ Office Mode**<br>*Office Mode* | 一鍵切換成低調的備忘錄風格，適合在公司或學校使用。<br>*One-click switch to a discreet memo-style UI for work or school.* |
| **📲 PWA 支援**<br>*PWA Support* | 可安裝到手機主畫面，全螢幕、無干擾、離線可用。<br>*Installable to home screen, fullscreen, distraction-free, and offline-capable.* |
| **☁️ 雲端自動同步**<br>*Auto Cloud Sync* | 使用 Supabase 背景同步，無需登入，換手機也能自動接續資料。<br>*Background sync via Supabase. Cross-device tracking with no login required.* |
| **💾 本地資料備份**<br>*Local Backup* | 一鍵匯出 / 匯入 JSON。<br>*One-click JSON export / import.* |

---

## 📱 使用方式 · How to Use

| 步驟 · Step | 操作說明 · Instructions |
| :---: | :--- |
| **1** | 開啟 App，查看今日應進行的訓練項目（Push / Pull / Legs）<br>*Open the app and check today's rotation.* |
| **2** | 依照動態課表訓練，記錄重量與次數，並使用休息計時器<br>*Train with the dynamic log, record your stats, and use the rest timer.* |
| **3** | 完成後點擊 **STAMP TODAY** 蓋章（或使用「應急訓練」）<br>*Tap **STAMP TODAY** upon completion (or use the Emergency Stamp).* |
| **4** | 訓練後記錄蛋白質攝取量<br>*Log your post-workout protein intake.* |
| **5** | 睡前打勾「收機再瞓」、「無咖啡因」與「冷卻」項目<br>*Check off wind-down habits before bed.* |
| **6** | 隨時查看 7 天摘要了解整體進度<br>*Review the 7-Day Summary anytime to track your progress.* |

---

## 🚀 部署方式 · Deployment

本專案為純靜態網頁，推薦使用 **Vercel + GitHub** 部署（Netlify / GitHub Pages 亦可）。
*This is a static site. Deploying via Vercel + GitHub is recommended (Netlify / GitHub Pages also work).*

1. **將專案推送到 GitHub** (*Push the project to GitHub*)
2. **在 Vercel 連接該 Repository 並部署** (*Connect the repo in Vercel and deploy*)
3. **部署完成後，在手機瀏覽器開啟網址並加入主畫面** (*Open the URL on your mobile browser and add it to your home screen*)

> **⚠️ 注意 · Note**
> 每次更新程式碼後，記得將 `CACHE_NAME` 版本號加一（例如 `v2` → `v3`），讓手機端更新到最新版本。
> *After every code update, bump the `CACHE_NAME` version (e.g., `v2` → `v3`) so installed devices pick up the latest build.*

---

## ☁️ Supabase 雲端同步設定 · Supabase Setup

1. **在 Supabase 建立新專案** (*Create a new Supabase project*)
2. **進入 SQL Editor，執行以下語法建立資料表** (*Open the SQL Editor and run the following snippet to create the table*):

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

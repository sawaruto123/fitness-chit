**健身單 · Daily Training Chit**

個人日常健身追蹤工具，採用香港復古車票風格設計，透過「蓋章」方式記錄每日訓練、蛋白質攝取、體重與睡眠習慣。

簡單、儀式感強，且支援雲端自動同步，適合長期使用。

### 功能特色

*   **彈性訓練循環**：Push → Pull → Legs 三天輪替，自動推進。即使跳過一天，也只需接續下一個循環。
    
*   **應急訓練打卡**：狀態極差時可使用 15 分鐘低強度選項，蓋上「應急」章，維持習慣而不產生罪惡感。
    
*   **動態課表與紀錄**：根據當日輪替自動顯示對應動作，並支援記錄重量與次數（附護腕/受傷保護提示）。
    
*   **休息計時器**：組間休息倒數，支援快速切換 60s / 90s / 120s / 180s。
    
*   **蛋白質追蹤**：快速新增按鈕（Shake、Meal、Snack）＋手動輸入，每日目標 150–180g，並有進度條顯示。
    
*   **體重記錄**：每日記錄並自動顯示與前次的變化趨勢。
    
*   **狀態與睡眠打卡**：
    
    *   收機再瞓（睡前遠離手機）連續紀錄
        
    *   訓前 6 小時無咖啡因
        
    *   睡前/訓練後 10 分鐘低強度冷卻
        
*   **7 天摘要**：快速查看過去 7 天的訓練次數、睡眠達標數、蛋白質平均值與體重變化。
    
*   **Office Mode**：一鍵切換成低調的備忘錄風格，適合在公司或學校使用。
    
*   **PWA 支援**：可安裝到手機主畫面，全螢幕、無干擾、離線可用。
    
*   **雲端自動同步**：使用 Supabase 背景同步，無需登入，換手機也能自動接續資料。
    
*   **本地資料備份**：一鍵匯出 / 匯入 JSON。
    

### 使用方式

1.  開啟 App，查看今日應進行的訓練項目（Push / Pull / Legs）。
    
2.  依照動態課表訓練，記錄重量與次數，並使用休息計時器。
    
3.  完成後點擊「STAMP TODAY」蓋章（或使用「應急訓練」）。
    
4.  訓練後記錄蛋白質攝取量。
    
5.  睡前打勾「收機再瞓」、「無咖啡因」與「冷卻」項目。
    
6.  隨時查看 7 天摘要了解整體進度。
    

### 部署方式

本專案為純靜態網頁，推薦使用 **Vercel + GitHub** 部署：

1.  將專案推送到 GitHub。
    
2.  在 Vercel 連接該 Repository 並部署。
    
3.  部署完成後，在手機瀏覽器開啟網址並加入主畫面。
    

> 每次更新程式碼後，記得在 將 CACHE\_NAME 版本號加一（例如從 v2 改成 v3），讓手機端更新最新版本。

### Supabase 雲端同步設定

1.  在 Supabase 建立新專案。
    
2.  進入 SQL Editor，執行以下語法建立資料表：
    

SQL

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   create table if not exists fitness_chits (    user_id text primary key,    updated_at timestamptz default now(),    data jsonb  );  alter table fitness_chits enable row level security;  create policy "Allow public access"   on fitness_chits for all   using (true) with check (true);   `

1.  在 index.html 中填入你的 SUPABASE\_URL 和 SUPABASE\_ANON\_KEY。
    
2.  重新部署即可啟用自動同步。
    

**English Version**

**健身單 · Daily Training Chit**

A personal daily fitness tracking tool with a retro Hong Kong MTR ticket aesthetic. It uses a “stamp” system to record workouts, protein intake, body weight, and wind-down habits in a simple and satisfying way.

### Features

*   **Flexible PPL Rotation**: Push → Pull → Legs cycle that auto-advances.
    
*   **Emergency Workout Stamp**: 15-minute low-intensity option for low-energy days.
    
*   **Dynamic Training Log**: Auto-displays exercises based on the day’s rotation with logging for weight and reps.
    
*   **Rest Timer**: Countdown timer with quick presets (60s / 90s / 120s / 180s).
    
*   **Protein Tracker**: Quick-add buttons + manual input with progress bar (target: 150–180g).
    
*   **Bodyweight Log**: Daily logging with automatic trend calculation.
    
*   **Wind-Down Tracker**: Phone away before bed, no caffeine 6 hours prior, and 10-minute cooldown.
    
*   **7-Day Summary**: Overview of workouts, sleep consistency, average protein, and weight changes.
    
*   **Office Mode**: One-click discreet memo-style interface.
    
*   **PWA Support**: Installable to home screen, fullscreen, and offline capable.
    
*   **Auto Cloud Sync**: Background syncing via Supabase using device ID (no login required).
    
*   **Local Backup**: One-click JSON export/import.
    

### How to Use

1.  Check today’s workout rotation.
    
2.  Train and log your sets/reps using the dynamic log and rest timer.
    
3.  Stamp when done (or use Emergency Stamp on bad days).
    
4.  Log protein intake.
    
5.  Check off wind-down habits at night.
    
6.  Review your 7-Day Summary for progress.
    

### Deployment

Deploy easily on Vercel, Netlify, or GitHub Pages. Recommended to use Vercel + GitHub for automatic deployments.

### Supabase Setup

Run the following SQL in Supabase to enable cloud sync:

SQL

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   create table if not exists fitness_chits (    user_id text primary key,    updated_at timestamptz default now(),    data jsonb  );  alter table fitness_chits enable row level security;  create policy "Allow public access"   on fitness_chits for all   using (true) with check (true);   `

Then add your Supabase URL and Publishable Key into the HTML file and redeploy.

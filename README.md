# 影潮 Shadow Tide

網頁版割草類肉鴿（Roguelite）。提著燈穿越五個夜晚：每關撐過 3 分鐘後魔王出現，打倒才能過關，武器與等級一路帶到下一關。

- 電腦：WASD／方向鍵移動，P 暫停，升級時按 1/2/3 選擇
- 手機：按住畫面任一處拖曳（浮動搖桿）

單一 `index.html`，純 Canvas，不需要建置工具。直接用瀏覽器打開即可。

## 結構（都在 index.html 的 `<script>` 裡）

| 區塊 | 內容 |
|---|---|
| `WEAPONS` / `PASSIVES` | 武器與被動的資料，加新技能從這裡開始 |
| `WEAPON_UPDATE` | 每種武器每格怎麼攻擊 |
| `STAGES` | 五個關卡：場景、怪的組成、魔王血量與招式 |
| `ENEMY_TYPES` / `spawnEnemies` | 敵人種類與生怪節奏 |
| `BOSS_ATTACKS` | 魔王招式（衝撞、召喚、彈幕、重擊） |
| `rollChoices` | 升級三選一的抽選規則 |
| `EVOLUTIONS` / `openChest` | 武器進化配方與寶箱（6 把武器、6 種進化） |
| `MAX_WEAPONS` / `MAX_PASSIVES` | 欄位上限：武器 4 把、被動 5 種 |

測試：網址後面加 `?debug`，開局就有滿級武器與配方被動、每關 20 秒、魔王血量 3 成；加 `?debug&stage=4` 從第 4 關開始。

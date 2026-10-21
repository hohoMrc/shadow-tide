# 影潮 Shadow Tide

網頁版割草類肉鴿（Roguelite）。提著燈穿越五個世界的夜晚：一局是一個世界的 5 關（X-1～X-5，每關 2 分半），第 3 關結束打中王、第 5 關結束打魔王，武器與等級在世界內一路帶到下一關。破了一個世界才會解鎖下一個，越後面越難、金幣越多。

- 電腦：WASD／方向鍵移動，P 暫停，升級時按 1/2/3 選擇、R 重抽
- 手機：按住畫面任一處拖曳（浮動搖桿）

每局撿到的金幣死掉也會保留，可以在「強化」商店買永久升級（生命、傷害、護甲、重抽、復活…）。

單一 `index.html`，純 Canvas，不需要建置工具。直接用瀏覽器打開即可。

## 結構（都在 index.html 的 `<script>` 裡）

| 區塊 | 內容 |
|---|---|
| `WEAPONS` / `PASSIVES` | 武器與被動的資料，加新技能從這裡開始 |
| `WEAPON_UPDATE` | 每種武器每格怎麼攻擊 |
| `WORLDS` | 五個世界：場景、難度倍率 `tier`、每關的怪 `mix`、中王 `mid` 與魔王 `boss` |
| `updateStage` / `stageDone` | 關卡流程：撐時間 → 打王 → 清場 → 下一關 |
| `ENEMY_TYPES` / `spawnEnemies` | 敵人種類與生怪節奏 |
| `BOSS_ATTACKS` | 魔王招式（衝撞、召喚、彈幕、重擊） |
| `ITEMS` / `useItem` | 地圖上隨機出現的道具 |
| `rollChoices` | 升級三選一的抽選規則 |
| `EVOLUTIONS` / `openChest` | 武器進化配方與寶箱（6 把武器、6 種進化） |
| `MAX_WEAPONS` / `MAX_PASSIVES` | 欄位上限：武器 4 把、被動 5 種 |
| `META_UPS` / `metaCost` | 局外成長：金幣商店的永久強化與價格 |
| `COIN_CHANCE` / `BOSS_COINS` / `SURVIVE_SECS` | 金幣來源：小怪掉落、魔王、存活獎勵 |

測試：網址後面加 `?debug`，開局就有滿級武器與配方被動、每關 20 秒、魔王血量 3 成；加 `?debug&world=2&stage=3` 從 2-3 開始。

存檔在瀏覽器的 localStorage：`shadowtide-worlds`（世界解鎖與最遠關卡）、`shadowtide-meta`（金幣與商店強化）。

# 影潮 Shadow Tide

網頁版割草類肉鴿（Roguelite）。提著燈，撐過黑夜裡湧來的影子，撐到 10:00 獲勝。

- 電腦：WASD／方向鍵移動，P 暫停，升級時按 1/2/3 選擇
- 手機：按住畫面任一處拖曳（浮動搖桿）

單一 `index.html`，純 Canvas，不需要建置工具。直接用瀏覽器打開即可。

## 結構（都在 index.html 的 `<script>` 裡）

| 區塊 | 內容 |
|---|---|
| `WEAPONS` / `PASSIVES` | 武器與被動的資料，加新技能從這裡開始 |
| `WEAPON_UPDATE` | 每種武器每格怎麼攻擊 |
| `ENEMY_TYPES` / `spawnEnemies` | 敵人種類與生怪節奏 |
| `rollChoices` | 升級三選一的抽選規則 |

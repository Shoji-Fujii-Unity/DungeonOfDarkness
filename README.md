# DUNGEON OF DARKNESS ― 闇の迷宮 ―

**[日本語](#日本語) | [English](#english)**

Wizardry風・一人称3DダンジョンRPG  
A Wizardry-like first-person 3D dungeon RPG

*単一HTMLファイル / Single HTML file / ブラウザだけで動作 / Runs in browser only*

</div>

---

# 日本語

## スクリーンショット構成
- **縦長レイアウト**主体(スマホ最適化・PCでは中央480px表示)
- レイキャストによる一人称3Dビュー + ミニマップ
- 部屋と通路がつながるフロア生成、階層ごとに変化する石壁・床、ドット絵モンスター
- ターン制コマンドバトル(攻撃/呪文/道具/逃走)

## 遊び方

1. `index.html` をブラウザで開くだけ(インストール・ビルド不要)
2. 「冒険を始める」→ パーティー4人を編成 → 「迷宮へ降りる」
3. 地下5階の玉座に封じられた**古代のリッチ王**を倒せ!

### キャラクターメイク
| 項目 | 内容 |
|---|---|
| 名前 | 直接入力 or 🎲 ランダム |
| 種族 | 人間 / エルフ / ドワーフ(基本ステータスが異なる) |
| 職業 | 戦士 / 魔法使い / 神官 / 盗賊 |
| ボーナス | 🎲 で 3d6 の獲得ポイントを HP(+5)/MP(+3)/ATK/DEF/SPD に自由配分 |

### 探索
- **移動**: ◀▶ でその場旋回、▲ で前進、↩ で180°反転
- **調べる**: 前方の階段・商人・治療師・宝箱を確認
- **罠**: 盗賊は感知して無力化しやすい
- **MAPボタン**: ミニマップ表示切替(探索済み範囲のみ表示)

### 戦闘
速度順にターンが回り、攻撃対象をタップで選択。呪文・道具も使用可。  
逃走は失敗すると手番を失う。ボス戦からは逃げられない!

### 装備システム
- スロット:**武器 / 両手武器 / 兜 / 鎧 / 盾** の5枠
- **両手武器と盾は排他**(どちらかを装備すると片方が外れて所持品に戻る)
- 職業ごとに装備できる物が異なる(例:巨剣=戦士のみ、ローブ=魔法使い/神官のみ)
- 宝箱やモンスター撃破で入手。階層が深いほど上位装備(ティア1〜3)が出る
- ステータス画面(メンバーチップをタップ)で装備の装着/解除

## システム

| 機能 | 説明 |
|---|---|
| 💾 セーブ | ローカルストレージに保存。💾ボタンで手動、階を降りると自動セーブ。「続きから冒険」で読込 |
| 🔊 サウンド | WebAudio合成音。ON/OFF切替・設定保存対応 |
| 🌐 多言語 | 日本語 ⇔ English を全UIで即時切り替え(設定保存) |
| ⌨ キーボード | ↑移動 / ←→旋回 / Enter調べる / M地図(PC用) |

## 技術メモ
- 依存ゼロの単一HTML(HTML + CSS + Vanilla JS)
- 迷宮はランダム化DFS迷路に部屋を追加して生成し、階段・施設は歩行可能な連結領域に配置
- 3D描画は canvas 上の DDA レイキャスト。施設スプライトは深度バッファで合成し、モンスターは低解像度キャンバスからドット絵として描画
- セーブデータ: `localStorage` キー `grimoire_souls_save_v1`
- ティア制ドロップ表・職業/種族ステータスは `<script>` 内の定義テーブルで簡単に拡張可能

## 更新履歴
- **v1.5** モンスターをドット絵に変更
- **v1.4** タイトルを Dungeon of Darkness に変更、部屋と通路のある迷宮生成、ダンジョンとモンスターの描画を刷新
- **v1.0** 初版

## ライセンス / License
このコードは自由に改変・再配布して構いません。  
Feel free to modify and redistribute.

---

# English

## Overview
A classic **Wizardry-style** first-person dungeon crawler that runs in a single HTML file.
Optimized for **portrait-mode smartphones** (displayed centered at 480px on desktop).

- Raycast-rendered 3D view + fog-of-war minimap
- Connected maze floors with chambers, floor-specific stone palettes, and pixel-art monsters
- Turn-based, speed-ordered party combat
- Party of 4 heroes with full character creation

## How to Play

1. Open `index.html` in any modern browser — no install, no build
2. "NEW GAME" → create your party of 4 → "ENTER DUNGEON"
3. Descend 5 floors and defeat the **Lich King** sealed on the deepest throne!

### Character Creation
| Item | Details |
|---|---|
| Name | Type your own or roll 🎲 |
| Race | Human / Elf / Dwarf (different base stats) |
| Class | Fighter / Mage / Priest / Thief |
| Bonus | Roll 3d6 points, allocate freely to HP(+5)/MP(+3)/ATK/DEF/SPD |

### Exploration
- **Move**: ◀ ▶ turn, ▲ step forward, ↩ u-turn
- **LOOK**: check stairs, merchant, healer or chests ahead
- **Traps**: Thieves are skilled at spotting them
- **MAP button**: toggle minimap (explored area only)

### Combat
Turns resolve by SPD. Tap a target to attack; cast spells or use items.  
Failed escapes waste your turn — and you can't flee from the boss!

### Equipment System
- 5 slots: **Weapon / Two-handed / Helm / Armor / Shield**
- **Two-handed weapons and shields are mutually exclusive** (equipping one unequips the other back to party storage)
- Each class has equipment restrictions (e.g. Greatswords = Fighter only, Robes = Mage/Priest only)
- Loot from chests and monster drops; deeper floors yield higher-tier gear (Tier 1–3)
- Equip/unequip from the STATUS screen (tap a party member chip)

## Systems

| Feature | Description |
|---|---|
| 💾 Save | LocalStorage. Manual via 💾, auto-save on descent. "CONTINUE" to load |
| 🔊 Sound | WebAudio-synthesized SFX with persistent ON/OFF toggle |
| 🌐 i18n | Full Japanese ⇔ English instant UI switching (persisted) |
| ⌨ Keyboard | ↑ move / ←→ turn / Enter look / M map (desktop) |

## Tech Notes
- Zero dependencies: single HTML file (HTML + CSS + vanilla JS)
- Floors use randomized DFS mazes with connected chambers; stairs and services are placed on reachable tiles
- DDA raycasting with floor-specific wall and floor palettes; landmarks and low-resolution pixel-art monsters are drawn on canvas
- Save key: `localStorage` → `grimoire_souls_save_v1`
- Drop tables and race/class stats are plain data objects — easy to extend

## Changelog
- **v1.5** Monster sprites redrawn as pixel art
- **v1.4** Dungeon of Darkness title, connected room-and-corridor floors, and custom dungeon/monster visuals
- **v1.0** Initial release

## License
Feel free to modify and redistribute.  
*(このコードは自由に改変・再配布して構いません。)*
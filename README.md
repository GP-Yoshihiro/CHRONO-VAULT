# CHRONO-VAULT
３Dプログラムの後期課題プロジェクト

3本のマスターキーを集め、警備AIの目を盗んで保管庫から脱出する 3Dステルス脱出アクションです。

| 項目 | 内容 |
|---|---|
| エンジン | Unreal Engine 5.7 |
| 実装 | ブループリントのみ（C++なし） |
| プラグイン | UE標準内蔵のみ（追加インストール不要） |
| 起動 | `ChronoVault.uproject` をダブルクリック → `L_Title` または `L_ChronoVault` を開いてプレイ |

## 操作

| 操作 | キーボード・マウス | ゲームパッド |
|---|---|---|
| 移動 / 視点 | WASD / マウス | 左 / 右スティック |
| ジャンプ | Space | A |
| ダッシュ | Shift（長押し） | LB |
| 操作（レバー） | E | X |
| ポーズ | P / Tab | Menu |
| メニュー選択 | ↑↓ / W・S / Tab、決定は Enter / Space（マウスも可） | 十字キー / 左スティック、決定は A |
| 開発用リセット | R（1秒長押し） | なし |

## 進め方
1. **エントランスホール** 光るスイッチを踏んで扉を開け、Key001 を取る
2. **監視回廊** 警備AIをやり過ごし、移動床で縦穴を渡って Key002 を取る
3. **中央制御室** 2本のレバーを引いて隔壁を開け、Key003 を取る
4. **脱出ゲート** 3本の鍵で最終マスター扉を開け、脱出ポッドに入ればクリア

緑の光はセーブポイントです。HPが0になるとゲームオーバーになり、最後のセーブ時点から再開できます。

## フォルダ構成

```
ChronoVault.uproject
Config/                  プロジェクト設定
Documents/               仕様書・課題資料・実装ガイド
Content/
├ ChronoVault/           このゲームで制作したアセット
│ ├ Core/               GameMode, GameInstance, PlayerController
│ ├ Player/             BP_Player, BPI_Player
│ ├ Enemy/              BP_MyCharacter, AIController, BT, BB, BTT, BTD
│ ├ Gimmick/            扉, 鍵, スイッチ, レバー, 移動床, ダメージ床, ゴール
│ ├ Save/               BP_SavePoint, BP_MySaveGame
│ ├ Data/               DT_KeyStatus, S_KeyStatus
│ ├ UI/                 タイトル, HUD, ポーズ, ゲームオーバー, クリア
│ ├ Input/              IMC_MyDefault, IA_*
│ ├ Environment/        BP_TileField（壁・床パネルの自動配置）
│ ├ Materials/          Master / Instances / Characters
│ ├ Meshes/             SM_Key
│ ├ Effects/            N_SaveLight, M_SaveLight
│ ├ Audio/              BGM / SE
│ └ Levels/             L_Title, L_ChronoVault
├ Characters/            UE標準マネキン（使用分のみ）
└ Fab/                   Fabの無料素材（使用分のみ・1024px以下に軽量化）
  ├ SciFiHallway_Apoc/
  └ SciFiLite_LumaxStudio/
```

## 使用素材
- Sci FI Hallway Asset Pack（Apoc / Fab 標準ライセンス）
- Sci-Fi Lite Sample Pack（Lumax Studio / Fab 標準ライセンス）

Fabの素材ファイルは再配布できないため、このリポジトリは非公開で運用してください。

仕様書の各項目と実装の対応は [Documents/実装ガイド.md](Documents/実装ガイド.md) を参照してください。

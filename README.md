# UPC-E → UPC-A 変換ツール

UPC-E コード（6 桁）を UPC-A コード（12 桁）に変換し、バーコードを表示する Web アプリケーションです。

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/llongmane584/upc-e-a-converter)

## 特徴

- **リアルタイム変換**: UPC-E（6 桁）から UPC-A（12 桁）への変換
- **アニメーション表示**: 変換過程を視覚的に理解できるアニメーション
- **バーコード生成**: 変換結果のバーコードを自動生成・表示
- **パターン対応**: 全 5 パターンの変換ルールに対応
- **モバイル対応**: レスポンシブデザインで 767px 以下の画面に最適化
- **チェックディジット**: 自動計算・検証機能

## 変換パターン

UPC-E の最後の桁（P₆）により以下のパターンで変換されます：

| P₆      | 変換パターン                        |
| ------- | ----------------------------------- |
| 0, 1, 2 | `0 + X₁X₂ + P₆ + 0000 + X₃X₄X₅ + C` |
| 3       | `0 + X₁X₂X₃ + 00000 + X₄X₅ + C`     |
| 4       | `0 + X₁X₂X₃X₄ + 00000 + X₅ + C`     |
| 5-9     | `0 + X₁X₂X₃X₄X₅ + 0000 + P₆ + C`    |

_C = チェックディジット（自動計算）_

## 使用方法

### オンライン使用

1. ブラウザで `index.html` を開く
2. UPC-E コード（6 桁）を入力フィールドに入力
3. 「変換開始」ボタンをクリック
4. アニメーションで変換過程を確認
5. 生成された UPC-A コードとバーコードを確認

### ローカル実行

```bash
# リポジトリをクローン
git clone https://github.com/llongmane584/upc-e-a-converter.git

# ディレクトリに移動
cd upc-e-a-converter

# ブラウザでindex.htmlを開く
open index.html
```

または、お好みの HTTP サーバーを使用：

```bash
# Python 3の場合
python -m http.server 8000

# Node.jsのserveパッケージを使用
npx serve .
```

## 技術仕様

### 依存関係

- **JsBarcode** (v3.11.6): バーコード生成ライブラリ
- **Google Fonts**: Noto Sans JP フォント

### ブラウザ対応

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

### 機能

- **入力検証**: 数字のみ受付、自動フォーカス移動
- **リアルタイム変換**: 入力完了時の即座変換
- **アニメーション制御**: 速度調整（0.5x - 3x）
- **エラーハンドリング**: ライブラリ読み込み失敗時のフォールバック表示

## ファイル構成

```
upc-e-a-converter/
├── index.html          # メインアプリケーション
├── README.md           # プロジェクト説明
└── CLAUDE.md          # 開発ガイドライン
```

## 開発

### 貢献方法

1. このリポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

### バグ報告

バグを見つけた場合は、[Issues](https://github.com/llongmane584/upc-e-a-converter/issues)で報告してください。

## 参考資料

- [GS1 General Specifications (PDF)](https://www.gs1jp.org/assets/img/pdf/GS1_General_Specifications.pdf)
- [UPC-E Wikipedia](https://en.wikipedia.org/wiki/Universal_Product_Code#UPC-E)

## ライセンス

このプロジェクトは MIT ライセンスの下で公開されています。詳細は[LICENSE](LICENSE)ファイルを参照してください。

## 作者

[@llongmane584](https://github.com/llongmane584)

---

⭐ このプロジェクトが役に立った場合は、スターをつけていただけると嬉しいです！

# PDF → JPG Converter (Client‑side)

## 概要

ブラウザだけで **PDF をページ単位の JPG 画像に変換** できるシングルページアプリです。すべての処理がクライアントサイドで完結するため、ファイルはインターネットへ送信されません。

|            | 使用技術                                 |
| ---------- | ------------------------------------ |
| UI         | HTML / Tailwind CSS                  |
| PDF レンダリング | pdf.js **v2.16 (Legacy UMD build)**  |
| 画像保存       | Vanilla JavaScript `canvas.toBlob()` |
| 一括ダウンロード   | JSZip / FileSaver.js                 |

---

## 特徴

* **バックエンド不要** : 静的ホスティング (GitHub Pages など) で即公開可能。
* **ドラッグ & ドロップ** とファイル選択の両方に対応。
* **高解像度出力** : `scale` 値を調整して画像の解像度を変更可能。
* **ページ個別 DL & 一括 ZIP DL** : ワンクリックでまとめて取得できます。

---

## クイックスタート

1. このリポジトリをクローン or ZIP ダウンロード。
2. `index.html` をブラウザで開く。
3. PDF をドロップまたはクリックで選択。
4. サムネイルが生成され、ページ単位で保存 or "すべてを ZIP でダウンロード" ボタンで一括取得。

> **TIP:** オフラインで使う場合は、下記の「オフライン利用」を参照して CDN 依存を削除してください。

---

## ディレクトリ構成（最小例）

```
project/
├─ index.html   # メインファイル（UI & ロジック）
├─ README.md    # このドキュメント
└─ libs/        # オフライン運用時にライブラリを配置 (任意)
```

---

## オフライン利用

CDN を使わずに完全オフラインで動かしたい場合は次の手順を実施:

1. `pdf.min.js` / `pdf.worker.min.js` / `jszip.min.js` / `FileSaver.min.js` を `libs/` フォルダーに保存。
2. `index.html` 内の `<script src="https://…">` を相対パス (`./libs/pdf.min.js` など) に書き換え。
3. Tailwind CSS もオフライン化したい場合は、事前ビルド済みの `tailwind.min.css` を同様に配置。

---

## カスタマイズヒント

| 目的              | 方法                                                               |
| --------------- | ---------------------------------------------------------------- |
| 出力画像の解像度を変更     | `page.getViewport({ scale: 2 })` の `scale` 値を変更 (例: 3 で 300% 拡大) |
| PNG で保存したい      | `canvas.toBlob(cb, "image/png")` に変更                             |
| サムネイルの UI を変更   | `thumbs` セクションの生成部分を編集                                           |
| 1 ファイルずつ自動命名したい | `page-${pageNum}.jpg` の命名ロジックを変更                                 |

---

## 既知の課題

* **大容量 PDF** (100MB 以上 / 数百ページ) ではメモリ使用量が増大し、ブラウザがフリーズする可能性があります。
* **iOS Safari** ではドラッグ & ドロップがサポートされていません (ファイル入力は可)。
* pdf.js v2.x を採用しているため、将来的な API 変更には手動アップデートが必要です。

---

## ライセンス

MIT License

---

### クレジット

* [Mozilla pdf.js](https://mozilla.github.io/pdf.js/)
* [Tailwind CSS](https://tailwindcss.com/)
* [JSZip](https://stuk.github.io/jszip/)
* [FileSaver.js](https://github.com/eligrey/FileSaver.js/)

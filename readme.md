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

## 既知のバグ

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

# PDF → JPG Converter (Client‑side)

ブラウザ上だけで **PDF をページ単位の JPG 画像に高速変換** できる、完全クライアントサイド完結型のシングルページアプリケーション（SPA）です。ファイルが外部サーバーに送信されることは一切ないため、機密性の高いドキュメントでも安全に処理できます。

---

## ⚡ 特徴

*   **完全ローカル処理** : バックエンドサーバーは不要。GitHub Pages や Netlify などの静的ホスティングで即座に公開・運用可能です。
*   **スムーズな UX** : ファイルのドラッグ＆ドロップと、クリックによるファイル選択の両方に対応。
*   **賢いファイル命名** : アップロードされた元の PDF 名を自動で引き継ぎ、各画像（`ファイル名-page-X.jpg`）や一括ダウンロード時の ZIP（`ファイル名.zip`）を出力します。
*   **高解像度レンダリング** : `scale: 2` 設定によるクリアな画像出力。
*   **柔軟な保存オプション** : 必要なページだけの個別保存と、全ページをまとめた一括 ZIP ダウンロードの双方に対応。

## 🛠️ 技術スタック

| 役割 | 使用技術 | 備考 |
| :--- | :--- | :--- |
| **UI / Styling** | HTML5 / Tailwind CSS | レスポンシブ対応のクリーンな UI |
| **PDF レンダリング** | [pdf.js](https://mozilla.github.io/pdf.js/) (v2.16 Legacy UMD) | Canvas への高度な描画処理 |
| **画像生成** | Vanilla JavaScript | `canvas.toBlob()` によるネイティブ変換 |
| **アーカイブ化** | [JSZip](https://stuk.github.io/jszip/) / [FileSaver.js](https://github.com/eligrey/FileSaver.js/) | ブラウザ側での即時 ZIP 生成・保存 |

## 🚀 クイックスタート


### 1. 実行
1. `index.html` をブラウザで開きます（ダブルクリックで OK）。
2. 変換したい PDF ファイルをドロップ、またはエリアをクリックして選択します。
3. 自動で生成されるサムネイルから個別保存するか、「すべてを ZIP でダウンロード」ボタンを押して一括取得します。

## ⚠️ 留意事項・既知の制限

* **大容量ファイルの処理**: 数百ページに及ぶ PDF や、極端にファイルサイズが大きいドキュメント（100MB〜）を一度に処理すると、ブラウザのメモリ上限に達してフリーズする場合があります。その場合はあらかじめ PDF を分割してからの処理をおすすめします。
* **モバイル対応**: iOS Safari 等のモバイル環境では仕様上ドラッグ＆ドロップ操作が制限されるため、ファイル選択ボタン（タップ）によるアップロードを利用してください。

---

## 📄 ライセンス
MIT License

---

### 💕 クレジット

* [Mozilla pdf.js](https://mozilla.github.io/pdf.js/)
* [Tailwind CSS](https://tailwindcss.com/)
* [JSZip](https://stuk.github.io/jszip/)
* [FileSaver.js](https://github.com/eligrey/FileSaver.js/)

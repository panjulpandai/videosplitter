# Station Split Marker

A single-file, browser-based tool for marking station/step split points in work-instruction videos. Load a video, scrub through it, mark where each station begins, and export a timestamp script you can use to cut clips in your video editor.

Includes optional AI assistance: upload an SRT subtitle file and let an AI model suggest split points based on the transcript content.

日本語の説明は下にあります (Japanese instructions below).

## Features

- Play, scrub, and step through video frame-by-frame (keyboard shortcuts included)
- Mark split points with one click or press `M`
- Rename, reorder, and remove stations
- Export results as CSV or a plain-text script with start/end/duration timestamps
- Optional AI-assisted splitting from an SRT transcript (Groq or Google Gemini)
- Bilingual UI (English / Japanese), toggle in the top right
- Everything runs locally in your browser — videos are never uploaded anywhere

## Getting started

1. Download `index.html` from this repo
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari) — no server or install needed
3. Load your video file
4. (Optional) Load a matching `.srt` subtitle file for AI-assisted splitting

## Usage

### Manual marking

- **Space** — play / pause
- **← / →** — step backward / forward 1 second
- **M** or the "Mark split here" button — add a split point at the current time

Each marked split becomes a row in the *Stations* table. Click the timestamp to jump to it, edit the name inline, or remove it.

### AI-assisted marking (optional)

1. Upload an `.srt` file with the same content/timing as your video
2. Choose a provider (Groq or Google Gemini) and paste your API key
3. Click "Suggest splits from transcript (AI)"

The AI reads the transcript and proposes station boundaries with descriptive names based on the spoken content. You can review, edit, add, or remove any of the suggestions afterward.

#### Getting an API key

- **Groq** (free tier available): create a key at [console.groq.com/keys](https://console.groq.com/keys)
- **Google Gemini** (free tier available): create a key at [aistudio.google.com/apikey](https://aistudio.google.com/apikey)

API keys are kept in memory in your browser tab only — they are never saved to disk and are not sent anywhere except directly to the chosen provider's API.

### Export

- **Export CSV** — spreadsheet-friendly list of station name, start, end, duration
- **Export text script** — human-readable script with the same information

Use the exported timestamps to cut your video into per-station clips in your editing software.

## Notes

- API keys are stored only in memory for the current browser tab/session and must be re-entered after a page reload.
- Model IDs for the AI providers may change over time as providers retire old models. If AI suggestions stop working, check the provider's current model list and update the model name in `index.html` (search for `model:` in the script).

---

## 日本語

作業手順動画の工程（ステーション）の分割位置をマークするためのブラウザ完結型ツールです。動画を読み込み、再生・スクラブしながら各工程の開始位置をマークし、編集ソフト用のタイムスタンプ一覧として書き出せます。

字幕(SRT)ファイルをアップロードすると、AIが文字起こし内容から分割案を提案する機能も使えます。

### 特徴

- 動画の再生・スクラブ・1秒単位の移動（キーボードショートカット対応）
- クリックまたは `M` キーで分割点をマーク
- 工程名の編集・並び替え・削除
- CSVまたはテキスト原稿として、開始・終了・長さ付きで書き出し
- SRT字幕からAIが分割案を提案（Groq または Google Gemini）
- 日英バイリンガルUI（右上で切り替え）
- すべてブラウザ内で処理され、動画はどこにもアップロードされません

### 使い方

1. このリポジトリから `index.html` をダウンロード
2. 任意のモダンブラウザ（Chrome、Edge、Firefox、Safariなど）で開く（サーバーやインストール不要）
3. 動画ファイルを読み込む
4. （任意）同じ内容の `.srt` 字幕ファイルを読み込むとAI分割提案が使えます

### 手動マーク

- **Space** — 再生・一時停止
- **← / →** — 1秒戻る・進む
- **M** または「ここで分割をマーク」ボタン — 現在位置に分割点を追加

マークした分割は「工程一覧」テーブルに表示されます。開始時刻をクリックでその位置に移動、工程名は直接編集、不要な行は「削除」できます。

### AIによる分割提案（任意）

1. 動画と同じ内容・タイミングの `.srt` ファイルをアップロード
2. プロバイダー（Groq または Google Gemini）を選び、APIキーを入力
3. 「文字起こしから分割を提案（AI）」をクリック

AIが文字起こしを読み、内容に基づいた工程名と分割位置を提案します。提案後も自由に編集・追加・削除できます。

#### APIキーの取得方法

- **Groq**（無料枠あり）: [console.groq.com/keys](https://console.groq.com/keys) でキーを作成
- **Google Gemini**（無料枠あり）: [aistudio.google.com/apikey](https://aistudio.google.com/apikey) でキーを作成

APIキーはブラウザのタブ内メモリにのみ保持され、保存されることはなく、選択したプロバイダーのAPI以外には送信されません。

### 書き出し

- **CSVを書き出す** — 工程名・開始・終了・長さの一覧（表計算ソフト向け）
- **テキスト原稿を書き出す** — 同内容を読みやすいテキスト形式で

書き出したタイムスタンプを使って、編集ソフトで動画を工程ごとのクリップに分割してください。

### 補足

- APIキーはブラウザタブのメモリ内にのみ保持されるため、ページを再読み込みすると再入力が必要です。
- AIプロバイダーのモデルIDは時間とともに変更・廃止される場合があります。AI提案が動作しなくなった場合は、プロバイダーの最新モデル一覧を確認し、`index.html` 内の `model:` を検索して更新してください。

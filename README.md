# my-tools

ブラウザで使えるPDF編集・パスワード生成・QRコード読み取り・画像編集のツール集です。

## 各ツールの機能

- **PDFペン**：PDFを開き、ペンや蛍光ペンで書き込んで、編集したPDFを保存できます。
- **パスワード作成**：文字数や記号の種類・個数を指定してパスワードを生成できます。パスフレーズの生成にも対応しています。生成履歴はタブ内のメモリに保持し、再読み込みやタブ終了で消えます。
- **QRリンクリーダー**：QRコード画像からURLを読み取り、結果をコピーできます。
- **画像編集**：画像の拡大・縮小、PNG・JPEG・WebPへの形式変換、画質調整・圧縮ができます。

トップページのカードから各ツールを開けます。各ツールはブラウザ上で動作し、アプリのインストールは不要です。

## 公開先

https://my-tools-95v.pages.dev/

## Cloudflare Pages

GitHubの `calltella/my-tools` と連携し、`main` へのpushで自動デプロイします。

| 設定 | 値 |
| --- | --- |
| プロジェクト名 | `my-tools` |
| 本番ブランチ | `main` |
| フレームワーク | なし |
| ビルドコマンド | 空欄（ビルド不要） |
| 出力ディレクトリ | `.` |
| ルートディレクトリ | 空欄（リポジトリ直下） |

各ツールはサブディレクトリの `index.html` で提供します。

### 更新を公開する手順

HTMLなどを編集したら、変更をコミットしてGitHubへpushします。

```bash
git add -A
git commit -m "Update tools"
git push origin main
```

Cloudflare PagesがGitHubの `main` ブランチを取得して自動デプロイします。ビルド作業は不要です。デプロイ状況はCloudflare管理画面の **Workers & Pages → my-tools → Deployments** で確認できます。

## ツールのフォルダ

| フォルダ | 内容 |
| --- | --- |
| `image-editor/` | 画像のリサイズ・形式変換・圧縮 |
| `pdf-annotator/` | PDFへのペン・蛍光ペンによる書き込み |
| `password-generator/` | パスワード・パスフレーズ生成 |
| `qr-code-reader/` | QRコード画像からURLを読み取り |

変更前のURLは `_redirects` で新しいURLへ転送します。

| 変更前 | 変更後 | 理由 |
| --- | --- | --- |
| `image/` | `image-editor/` | 画像編集ツールであることを明確にするため |
| `pdf-edit/` | `pdf-annotator/` | PDFへの書き込み・注釈が主な機能のため |
| `qrcode-reader/` | `qr-code-reader/` | 単語をハイフンで区切る命名に揃えるため |

`password-generator/` は機能に合った名前なので変更していません。フォルダ名に合わせて、トップページのリンクも更新しています。

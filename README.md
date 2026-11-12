# my-tools

ブラウザで使えるPDF編集・パスワード生成・QRコード読み取り・画像編集のツール集です。

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

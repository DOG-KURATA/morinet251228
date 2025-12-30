# modernize-bootstrap

## 変更履歴

### blog-posts.html

1. **コンテンツ上部の空白を削除**
   - セクションの`pt-5 pt-md-14 pt-lg-12`（上部パディング）を削除
   - タイトル削除後の余分な空白を解消

2. **一番上のカード列を4カラムに変更**
   - `col-lg-4`（3カラム）から`col-lg-3`（4カラム）に変更
   - 4つのブログカードが横並びで表示されるように

### blog-posts-4align-items_stretch.html（テスト版）

- CSS Gridの`align-items: stretch`を使用したレイアウト調整テスト
- カードの高さを揃えるための実験的な実装
- サイドメニューに「Posts4」として追加

### サイドメニュー

- Blogサブメニューに「Posts4」リンクを追加

### タグフィルタリングシステム

- カードのタグをクリックすると、そのタグでフィルタリングされた一覧ページへ遷移
- Recent ArticlesとLocal Topicsは別々のコンテンツソースとして管理
- フィルタリング時にはヘッダータイトルが「タグ名 の記事一覧」に変更
- 「フィルターを解除」ボタンで通常表示に戻る

### ページネーション

- Recent Articlesに30枚のカードを追加
- グリッドビュー: 1ページ9件表示（4ページ）
- リストビュー: 1ページ10件表示（3ページ）
- ビュー切り替え時に対応するページネーションも切り替わる

### ロゴリンク

- ヘッダー/フッターのmorinetロゴクリックで`blog-posts.html`へ遷移

## Git設定

### リモートリポジトリ構成

| リモート名 | 用途 |
|-----------|------|
| origin | GitLab（正・本番・CI/CD） |
| github | GitHub（副・配布／共有） |

### プッシュコマンド

| コマンド | 動作 |
|---------|------|
| `git push` | GitLabのみ |
| `git push github` | GitHubのみ |
| `git pushall` | 両方同時 |

### alias設定

```bash
git config alias.pushall '!git push origin && git push github'
```

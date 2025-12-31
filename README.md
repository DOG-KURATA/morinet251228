# modernize-bootstrap

## 変更履歴

### blog-posts.html

1. **コンテンツ上部の空白を削除**
   - セクションの`pt-5 pt-md-14 pt-lg-12`（上部パディング）を削除
   - タイトル削除後の余分な空白を解消

2. **一番上のカード列を4カラムに変更**
   - `col-lg-4`（3カラム）から`col-lg-3`（4カラム）に変更
   - 4つのブログカードが横並びで表示されるように

3. **全カードのリンク先を統一**
   - 全てのカード（画像・タイトル）のリンク先を`blog-detail.html`に統一
   - 対象セクション:
     - フィーチャーコンテンツ（メインバナー + 4枚のカード）
     - Local Topics（カルーセル）
     - Event Pick Up（6枚のカード）
     - Recent Articles（グリッドビュー・リストビュー）

### blog-detail.html

- `frontend-blogdetailpage.html`と同じデザインで新規作成
- 左サイドバー（管理画面ナビゲーション）を保持
- コンテンツ構成:
  - バナーセクション（`bg-primary-subtle`背景）
  - タグ・タイトル・閲覧数・コメント数・日付を中央配置
  - 画像が下にはみ出すスタイル（`mb-n11`）
  - 詳細セクション: 左側に著者情報・目次・シェア（col-lg-4）、右側に記事本文（col-lg-8）
  - Developセクション（CTA: Member Login, Register as Member）

### blog-posts-4align-items_stretch.html（テスト版）

- CSS Gridの`align-items: stretch`を使用したレイアウト調整テスト
- カードの高さを揃えるための実験的な実装
- サイドメニューに「Posts4」として追加

### サイドメニュー

- Blogサブメニューに「Posts4」リンクを追加
- Blogサブメニューに「Detail」リンクを追加（blog-detail.html）

### タグフィルタリングシステム

- カードのタグをクリックすると、そのタグでフィルタリングされた一覧ページへ遷移
- Recent Articles、Local Topics、Event Pick Upは別々のコンテンツソースとして管理
- フィルタリング時にはヘッダータイトルが「タグ名 の記事一覧」に変更
- 「フィルターを解除」ボタンで通常表示に戻る
- フィルタリング時は右サイドバーを非表示にし、メインコンテンツを全幅表示

### ページネーション

- Recent Articlesに30枚のカードを追加
- グリッドビュー: 1ページ9件表示（4ページ）
- リストビュー: 1ページ10件表示（3ページ）
- ビュー切り替え時に対応するページネーションも切り替わる

### ロゴリンク

- ヘッダー/フッターのmorinetロゴクリックで`blog-posts.html`へ遷移

---

## ページ構成

| ファイル | 説明 |
|---------|------|
| `blog-posts.html` | ブログ一覧ページ（メイン） |
| `blog-detail.html` | ブログ詳細ページ（左サイドバー付き） |
| `blog-posts-4align-items_stretch.html` | カード高さ揃えテスト版 |
| `frontend-blogdetailpage.html` | フロントエンド用詳細ページ（参照元） |

---

## セクション構成（blog-posts.html）

### 1. フィーチャーコンテンツ
- メインバナー（左: 画像、右: 記事情報）
- 4枚のカード（`col-lg-3`で横並び）

### 2. Local Topics
- Owl Carouselによるカルーセル表示
- タグクリックで`?tag=タグ名&section=local-topics`に遷移

### 3. Event Pick Up
- 6枚のカード（`col-lg-2`で横並び）
- イベント期間表示付き
- タグクリックで`?tag=タグ名&section=event-pickup`に遷移

### 4. Recent Articles
- グリッドビュー / リストビュー切り替え可能
- ページネーション付き
- タグクリックで`?tag=タグ名`に遷移（セクション指定なし）

---

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

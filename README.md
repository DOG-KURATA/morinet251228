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

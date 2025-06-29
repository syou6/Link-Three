# Lofi Boy Music - マイクロポートフォリオサイト

## プロジェクト概要

音楽クリエイター「Lofi Boy Music」のためのプレミアムマイクロポートフォリオサイトです。リンクツリースタイルをベースに、プロフェッショナルな音楽クリエイターのブランディングを強化したデザインになっています。

## 主要機能

### コア機能
- **ヒーローセクション**: フルスクリーンのグラデーション背景with音楽的要素
- **SNSリンク集**: YouTube, Instagram, TikTok, X(Twitter)への統合リンク
- **コンテンツ表示**: 各プラットフォームの最新投稿を魅力的に表示
- **ブランドカスタマイズ**: 5種類のカラーテーマ選択
- **ダークモード**: 完全対応のダーク/ライトモード切替

### 高度な機能
- **YouTube動画モーダル**: 動画をサイト内で直接再生
- **Instagramカルーセル**: Swiper.jsによる滑らかな投稿表示
- **アニメーション**: スクロール連動アニメーションとマイクロインタラクション
- **音波エフェクト**: 音楽クリエイターらしいビジュアル要素
- **レスポンシブデザイン**: モバイルファースト設計

## ファイル構造

```
src/
├── index.html          # メインHTMLファイル（エントリーポイント）
├── YOUWARE.md         # プロジェクトドキュメント
└── assets/            # アセットディレクトリ（将来の拡張用）
```

## 使用技術スタック

### フロントエンド
- **HTML5** - セマンティックマークアップ
- **Tailwind CSS 4.0** - ユーティリティファーストCSS
- **JavaScript (Vanilla)** - インタラクション処理
- **CSS Variables** - 動的テーマシステム

### 外部ライブラリ
- **Swiper.js** - カルーセル機能
- **Font Awesome 6.5** - アイコンライブラリ
- **Google Fonts** - Inter & Noto Sans JP フォント

### 埋め込みAPI
- **YouTube IFrame API** - 動画再生機能
- **Instagram Embed API** - 投稿表示
- **TikTok Embed** - TikTok投稿表示
- **Twitter/X Embed** - ツイート表示

## デザインシステム

### カラーテーマ
サイトは5つのプリセットカラーテーマを提供：
1. **Purple** (デフォルト): `#8b5cf6` → `#7c3aed` → `#a78bfa`
2. **Pink**: `#ec4899` → `#db2777` → `#f472b6`
3. **Green**: `#10b981` → `#059669` → `#34d399`
4. **Orange**: `#f59e0b` → `#d97706` → `#fbbf24`
5. **Blue**: `#3b82f6` → `#2563eb` → `#60a5fa`

### アニメーション
- **スクロール連動アニメーション**: Intersection Observer使用
- **ホバーエフェクト**: Transform + Box-shadow
- **ページ遷移**: Smooth scrolling
- **ローディング**: CSS keyframes

## カスタマイズガイド

### プロフィール情報の変更

```html
<!-- ヒーローセクション内 -->
<h1 class="text-5xl md:text-6xl font-bold text-white mb-4">
    Lofi Boy Music <!-- ここを変更 -->
</h1>
<p class="text-xl md:text-2xl text-white/90 mb-8">
    🎵 Relaxing Beats & Chill Vibes 🎵 <!-- サブタイトル変更 -->
</p>
<p class="text-lg text-white/80 max-w-2xl mx-auto mb-12">
    <!-- 自己紹介文を変更 -->
    LofiとChillhopで心を癒す音楽を制作しています...
</p>
```

### SNSリンクの更新

```html
<!-- YouTube リンク例 -->
<a href="https://www.youtube.com/@YOUR_CHANNEL" target="_blank" class="social-link flex items-center group">
    <div class="social-icon youtube-gradient">
        <i class="fab fa-youtube"></i>
    </div>
    <div class="flex-grow">
        <h3 class="font-semibold text-lg mb-1">YouTube</h3>
        <p class="text-gray-600 dark:text-gray-400">@YOUR_HANDLE - 説明文</p>
    </div>
    <i class="fas fa-external-link-alt text-gray-400 group-hover:text-gray-600 transition-colors"></i>
</a>
```

### カラーテーマの追加

```html
<!-- 新しいカラーオプションを追加 -->
<span class="color-option" 
      style="background: linear-gradient(135deg, #新色1, #新色2);" 
      data-color="#新色1" 
      data-secondary="#新色2" 
      data-accent="#新色3">
</span>
```

## 高度なカスタマイズ

### YouTube API連携
実際のYouTube Data APIを使用する場合：

```javascript
// APIキーを設定
const YOUTUBE_API_KEY = 'YOUR_API_KEY';
const CHANNEL_ID = 'YOUR_CHANNEL_ID';

async function fetchYouTubeVideos() {
    const response = await fetch(
        `https://www.googleapis.com/youtube/v3/search?key=${YOUTUBE_API_KEY}&channelId=${CHANNEL_ID}&part=snippet&order=date&maxResults=4`
    );
    const data = await response.json();
    // 動画データを処理
}
```

### Instagram Graph API連携
Instagram Businessアカウントでの投稿取得：

```javascript
const INSTAGRAM_ACCESS_TOKEN = 'YOUR_ACCESS_TOKEN';
const INSTAGRAM_USER_ID = 'YOUR_USER_ID';

async function fetchInstagramPosts() {
    const response = await fetch(
        `https://graph.instagram.com/${INSTAGRAM_USER_ID}/media?fields=id,caption,media_type,media_url,thumbnail_url,timestamp&access_token=${INSTAGRAM_ACCESS_TOKEN}`
    );
    const data = await response.json();
    // 投稿データを処理
}
```

## パフォーマンス最適化

### 実装済み最適化
- **画像遅延読み込み**: Intersection Observer
- **CSS最適化**: Tailwind CSS purging
- **JavaScript最適化**: イベント委譲とメモ化
- **フォント最適化**: Google Fonts preload

### 推奨追加最適化
- **CDNキャッシュ**: 静的アセットのキャッシュ戦略
- **画像最適化**: WebP形式の使用
- **Service Worker**: オフライン対応
- **Lighthouse監査**: 定期的なパフォーマンスチェック

## SEO対策

### 基本設定
```html
<title>Lofi Boy Music - リラックス音楽クリエイター</title>
<meta name="description" content="Lofi Hip HopとChillhopで心を癒す音楽を制作。勉強・作業・リラックスにぴったりの音楽をお届けします。">
<meta name="keywords" content="LoFi, Chill Hop, リラックス音楽, 作業用BGM, 勉強用音楽">
```

### Open Graph設定
```html
<meta property="og:title" content="Lofi Boy Music">
<meta property="og:description" content="心を癒すLofi音楽クリエイター">
<meta property="og:image" content="プロフィール画像URL">
<meta property="og:url" content="サイトURL">
```

## 将来の拡張計画

### Phase 1: データ統合
- [ ] YouTube Data API実装
- [ ] Instagram Graph API統合
- [ ] TikTok API連携
- [ ] リアルタイムデータ更新

### Phase 2: 高度な機能
- [ ] 音楽プレイヤー統合
- [ ] Spotifyプレイリスト埋め込み
- [ ] ファンメッセージ機能
- [ ] イベント・ライブスケジュール

### Phase 3: バックエンド機能
- [ ] アクセス解析ダッシュボード
- [ ] アフィリエイトリンク管理
- [ ] コンテンツ管理システム
- [ ] ユーザー認証機能

## トラブルシューティング

### よくある問題

**Q: カラーテーマが保存されない**
A: ブラウザのローカルストレージが有効になっているか確認してください。

**Q: 埋め込みコンテンツが表示されない**
A: ネットワーク環境とCORSポリシーを確認してください。

**Q: モバイルでアニメーションが重い**
A: CSS `will-change`プロパティとGPUアクセラレーションを確認してください。

### デバッグ手順
1. ブラウザのデベロッパーツールでコンソールエラーを確認
2. ネットワークタブで埋め込みコンテンツの読み込み状況を確認
3. Lighthouseでパフォーマンス測定

## ブラウザサポート

### 対応ブラウザ
- **Chrome**: 88+
- **Firefox**: 84+
- **Safari**: 14+
- **Edge**: 88+

### 必要なフィーチャー
- CSS Grid & Flexbox
- Intersection Observer API
- CSS Variables
- ES6+ JavaScript

---

このドキュメントは、Lofi Boy Musicポートフォリオサイトの完全なガイドラインです。追加の質問やカスタマイズ要望がある場合は、YOUWARE.comまでお問い合わせください。
---
marp: true
theme: default
#header: "**ヘッダータイトル**"
#footer: "© Copyright xxxx All rights reserved."

size: 16:9
paginate: true

style: |
    section.title {
        justify-content: center;
        text-align: center;
    }

    section {
        justify-content: start;
    }

---
<!-- _class: title -->
# SSGのHugoで構築する私のblog



<!--
_color: white
_footer: 'Photo by Earl Lasala on Unsplash'
-->
![bg brightness:0.4](https://images.unsplash.com/photo-1600183309638-bb6dfca7e921?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=750&q=80)



---
# 自己紹介

- ITDで3年弱ドコモに参画
- 第2PD部として金融系のシステムを担当
  - CDD基盤
  - コンテナ実行基盤　etc

- 趣味として木工職人の道を邁進中
  - デスクシェルフ
  - ヘッドホンスタンド（写真）

![bg left:40% brightness:1.2](./20241218075057.jpg)


---
# 発表するに至った経緯

1. 加齢とともに、忘れてしまいがち。何回もググる
2. 技術的なメモはブログに残すよう心がける
3. 気づけば約2年ぐらい運用
4. 今っぽい技術を使う。知っておくとモテると思って紹介

バカも休み休み Yeah
https://yamada-tech-memo.netlify.app/

---
# アジェンダ

- SSGとは何か
- SSG登場の背景
- SSGのメリット
- SSGのツールHugoを使ったblog環境
  - 実際に運用している構成を説明
![bg right:40% brightness:1.2](https://images.unsplash.com/photo-1735977161893-d969d37f32c5?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)


---
## SSGとは何か

- Static Site Generator（Generation）
- 静的なhtmlやcssなどでサイトを構築する

---
## SSG登場の背景：CMSの覇者 WordPressの課題

- CMSにおけるWordPressのシェア84%
- WordPressはいわゆるLAMP構成（Linux、Apache、Mysql、PHP）
- 記事管理はデータベース
- クライアントがサイトにアクセスするたびにhtmlを***動的生成***
- 大量のリクエストはデータベースがボトルネックになり性能落ちがち
- データベースがあるので、スケールしにくい
- 構成要素が多く、セキュリティ対策が必要

上記のような課題を解決したい

---
## SSG登場の背景：環境がととのってきた

- GitHubを一般的に使うようになった
  - 馴染み深いgitコマンドを使える
- CI/CDが一般的になった
  - htmlやcssを自動で生成できる環境
- 無料、安価なホスティングサービス登場
  - Netlify
  - Vercel
  - S3,CloudFront
---
## SSGのメリット

- 表示スピードが速い
- CDNによりスケールしやすい
- セキュリティリスクが低い
  - 基本的にhtml、CSSで表現している。

---
## hugoによる環境構築

- hugoとは
  - golangで実装されたSSG
  - 他にGatsby（React）、jekyll（Ruby）なども有名
- hugoの特徴
  - markdownで記事を書ける
  - buildが速い

---
### 構成

Netlify：老舗のホスティングサービス

![](./wordpress-hugo-migration_002.jpg)


---
## 構成の良いところ

- 無料の範囲でできる
- 広告が入らないので精神的に安心
- 好みのエディタで書ける（例：VSC）
- 記事はGitHubで管理
- GitHubなので、プルリク、レビュー、マージなどの運用も可能
- 複数人で記事を書くこともできる
- GitHub ActionsでLintやリンク切れチェックなどのCIもまわせる
- ホスティングをVercelやS3＋CloudFrontなどへの変更も容易（ベンダロックイン回避）
- 企業のtechなblogにも使われているらしい

---
## 構成のイマイチなところ

- git、GitHub、markdownなどある程度の習熟が必要
- Netlifyはたくさん使うと課金が必要（例：ビルド300分を超える）
- スマホで書くには不向き

---
## おわりに

明日の自分は忘れている。

これからも明日の自分に書きます！

<!--
_footer: 'Photo by jet dela cruz on Unsplash'
-->
![bg left:40% brightness:1.2](https://images.unsplash.com/photo-1603852451827-102c34437985?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1400&q=80)

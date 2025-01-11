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


- 趣味として木工職人の道を邁進中
  - デスクシェルフ
  - ヘッドホンスタンド（写真）

![bg left:40% brightness:1.2](./20241218075057.jpg)


---
# 発表するに至った経緯

1. 加齢とともに、すぐに忘れてしまう。何回もググる
2. ググると負けた気になる。技術的なメモはブログに残すよう心がける
3. 気づけばブログを約2年ぐらい運用
4. システム開発やっているとブログの仕組みについて話す機会がないので、話してみたいと思った

---
# このLTで得られるもの

- SSGとは何かを知る
- hugoというツールの存在を知る
- 私のブログを読める（宣伝）
  - バカも休み休み Yeah（ https://yamada-tech-memo.netlify.app/ ）

---
# アジェンダ

- SSGとは何か
- SSG登場の背景
- SSGのメリット
- SSGのツールHugoとは
- 私のブログ環境
  - 実際に運用している構成を紹介
![bg right:40% brightness:1.2](https://images.unsplash.com/photo-1735977161893-d969d37f32c5?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)


---
## SSGとは何か

- Static Site Generator（Generation）
- あらかじめ静的なファイル（htmlやcssなど）を作成してサイトを構築する

---
## SSG登場の背景：CMSの覇者 WordPressの課題

- シェア84%　CMSにおける覇者
- いわゆるLAMP構成（Linux、Apache、Mysql、PHP）
- 記事管理はデータベース
- クライアントがサイトにアクセスするたびにhtmlを***動的生成***
- 動的生成のため、大量のリクエストはデータベースがボトルネックになり性能落ちがち
- 構成要素が多く、セキュリティ対策が必要
  - セキュリティパッチ適用が日々の運用になりがち

---
## SSG登場の背景：整う環境

- GitHubが一般的になった
  - 馴染み深いgitコマンドを使える
- CI/CDが一般的
  - htmlやcssを自動で生成できる環境
- 無料、安価なホスティングサービス
  - Netlify
  - Vercel
  - S3,CloudFront
---
## SSGのメリット

- 表示スピードが速い
  - 構成要素が少ない
- CDNでスケールしやすい
  - 静的ファイルの強み
- セキュリティリスクが低い
  - 基本的にhtml、CSSで表現している。

---
## hugoとは

- hugo is 何？
  - golangで実装されたSSG
  - 他にGatsby（React）、jekyll（Ruby）なども有名
- hugoの特徴
  - markdownで記事を書ける
  - buildが速い 約2500記事のbuildで約20秒。
```
                   |  EN   
-------------------+-------
  Pages            | 2476  


Built in 19447 ms
```
---
### 私のblog環境

記事をGitHubにPUSH → 自動でビルドしてNetlifyにデプロイ。

![](./wordpress-hugo-migration_002.jpg)


---
## この環境の良いところ

- 無料の範囲でできる
- 広告が入らないので精神的に良い
- 好みのエディタで書ける（例：VSC）
- 記事管理はGitHub
  - 複数人で記事を書くことができる
  - プルリク、レビュー、マージなどの運用も可能
  - GitHub Actionsで誤字脱字やデッドリンクのチェック等、CIをまわせる
- ホスティング先の変更も容易（ベンダロックイン回避）
- イケてる感（tech企業のblogに採用されている例もある）

---
## この環境のイマイチなところ

- GitHub、git、markdownなどある程度の習熟が必要
- スマホで書くには不向き
  - 手軽とは言えない
- 記事検索の実装はテクニックが必要
  - JavaScriptのライブラリFuse.js、Algoliaのような検索サービス
- 1文字変更するだけでも、全てのページを再作成
  - 無駄感はある
- Netlifyはたくさん使うと課金対象
  - 例：ビルド300分/1ヶ月を超える


---
## おわりに

明日の自分は忘れている。

これからも明日の自分に書きます！

<!--
_footer: 'Photo by jet dela cruz on Unsplash'
-->
![bg left:40% brightness:1.2](https://images.unsplash.com/photo-1603852451827-102c34437985?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1400&q=80)

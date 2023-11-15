# KEIZOKU-front

## モチベーション
「継続は力なり」という言葉の通り苦手なことでも継続して行えば積み重なって前よりも上手くいくようになるし楽しめるようになる。GithubのコントリビューショングラフやAtCoder ProblemsのHeatmapなど、やったことを記録してヴィジュアライズするような機能はあるが、一日でもやらない日があると空白が目立って悲しい気持ちになることがある。目的は毎日やることではなく、長期的に継続して力をつけることなので、少し間が空いても復帰したくなるような工夫のある機能を作りたい。

## フロントエンド
- Next.jsを使用
- SSRとSSGを両方同時に実現できる
    - SSR：情報更新等のAjaxリクエストを飛ばすページに適用
    - SSG：ダッシュボード等グラフヴィジュアライズのページに適用
    - 参考：[SPA, SSR, SSGって結局なんなんだっけ？](https://zenn.dev/rinda_1994/articles/e6d8e3150b312d)



## バックエンド

### アーキテクチャ
- Clean Architecture
    - 参考サイト: [bxcodec/go-clean-arch](https://github.com/bxcodec/go-clean-arch)

### 言語&フレームワーク
- Golang
- Gin
    - echoは使ったことがあるが、自分でdocumentを見て実装をしたいので今回はGinを使う
    - 興味のある企業がGinを使っているのも理由
    - echoとGinの違いと、選択理由を言えるようにする

### 認証
OIDC(OpenIDConnect)とパスワード認証を実装  
参考: [13 best practices for user account, authentication, and password management](https://cloud.google.com/blog/products/identity-security/account-authentication-and-password-management-best-practices?hl=en)

#### OIDC
- [github repository](https://github.com/dakario/gin-oidc/blob/0f798c990b95/ginoidc.go)
    - 実装を見てみると、oauthライブラリを用いてそれ以外の部分を実装している。RFCもしくはわかりやすいページで確認しながら見るのがよさそう。
- [30分でOpenID Connect完全に理解したと言えるようになる勉強会](https://speakerdeck.com/d_endo/30fen-deopenid-connectwan-quan-nili-jie-sitatoyan-eruyouninarumian-qiang-hui)
    - OIDCの解説

### パスワード認証
- [ソルト付きハッシュのソルトはどこに保存するのが一般的か](https://qiita.com/ockeghem/items/d7324d383fb7c104af58)
    - パスワードハッシュのソルトを扱う際の注意点

## インフラ
- AWS or GCP or etc...
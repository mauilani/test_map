# Mapboxを実装してみる

## 概要
TOPページにMapboxを使って地図を表示するまでの実装方法のメモです

### 参考サイト

- Mapbox
 　[Mapbox Top](https://www.mapbox.jp/
　 [YOLPJavaScriptマップAPIからMapbox GL JSへの移行ガイド](https://docs.mapbox.com/jp/yolp-to-mapbox/javascript/)

   [Mapbox GL JS クイックスタート](https://docs.mapbox.com/mapbox-gl-js/api/)
   上記移行ガイドよりこちらの方がよい
   
- 外部参考サイト
   [Mapbox GL JS）トークン取得と地点名の日本語表記](https://2ndart.hatenablog.com/entry/2020/07/01/163810)

###  テスト用のindex.html を用意


###  Mapbox アカウント作成
- アカウントを作成する。
    [Mapbox アカウント作成画面](https://account.mapbox.com/auth/signup/)

###  アクセストークンを取得する
- アカウント作成時にデフォルトのアクセストークンが作成されている
    [Access tokens](https://account.mapbox.com/access-tokens/)
    Default public token の値になります
    
    他資料
    [トークンやスコープについて](https://docs.mapbox.com/accounts/overview/tokens/#scopes)
    
 ###  index.htmlに実装する
 - Add Mapbox to your app or website 
    [インストール手順](https://www.mapbox.com/install/)
    
    1. 「JS web」を押下
    2. 「Use the Mapbox CDN」を押下
    3.  Include the GL JS files に従って以下を<head>にコピペ
```
 <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.1/mapbox-gl.js'></script>
 <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.1/mapbox-gl.css' rel='stylesheet' />
```

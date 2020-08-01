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

### 1.テスト用のindex.html を用意


### 2.Mapbox アカウント作成
- アカウントを作成する。
    [Mapbox アカウント作成画面](https://account.mapbox.com/auth/signup/)


### 3.アクセストークンを取得する
- アカウント作成時にデフォルトのアクセストークンが作成されている
    [Access tokens](https://account.mapbox.com/access-tokens/)
    Default public token の値になります
    
    他資料
    [トークンやスコープについて](https://docs.mapbox.com/accounts/overview/tokens/#scopes)
 
 
 ### 4.index.htmlに実装する
 - 下記ガイドの通りに行います。
　 [YOLPJavaScriptマップAPIからMapbox GL JSへの移行ガイド](https://docs.mapbox.com/jp/yolp-to-mapbox/javascript/)
 
  a. 地図を表示させるコンテナをdivタグとしてbody内に配置する。
```
<div id='map'></div>
```
  b. head内でmapbox-gl.jsとmapbox-gl.cssを読み込む。
```
<script src='https://api.mapbox.com/mapbox-gl-js/v1.11.1/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v1.11.1/mapbox-gl.css' rel='stylesheet' />
```
  c. body内に以下のJS<script>...</script>をコピペする
```
<body>
    <div id='map'></div>    /* 1の設定  */
    
    <script>
    /* アクセストークンの設定 */
    mapboxgl.accessToken = 'YOUR_MAPBOX_ACCESS_TOKEN';
    /* 地図を表示 */
    var map = new mapboxgl.Map({
        /* 地図を表示させる要素のid */
        container: 'map',
        /* 地図styleID。YOLPではLayerSetIdに相当する。*/
        style: 'mapbox://styles/mapbox/streets-v11',
        /* 地図の初期緯度経度[lng,lat] */
        center: [-74.50, 40],
        /* 地図の初期ズームレベル */
        zoom: 9
    });
    </script>
</body>
```
  d. 以上でコピペは完了
     同じ方法ですがステップごとに設定方法を説明しているページもあります。
     [インストール手順](https://www.mapbox.com/install/)
    (「JS web」を押下 =>「Use the Mapbox CDN」を押下してすすめる )
  
  e. 各パラメータを書き換える　以下、5番以降の手順
  
  
  ## 5.取得したデフォルトアクセストークンに書き換える
  - [Access tokens](https://account.mapbox.com/access-tokens/) のトークンの値をコピペします
 **変更前**
 ```
  /* アクセストークンの設定 */
  mapboxgl.accessToken = 'YOUR_MAPBOX_ACCESS_TOKEN';
 ```
  **変更後**
 ```
  /* アクセストークンの設定 */
  mapboxgl.accessToken = 'pk.eyJ1IjoibWF1aWxhbmkiL**********************';
 ```
 
 
 ## 6.container: 'map'  はdiv id='map'で指定したとおりで同じ
 
 
 ## 7. 地図を日本語表記に変換する　Style URL を変換する
-「スタイル」ページに移動
  [Styles](https://studio.mapbox.com/)
  
- ページ右側のTools & resourcesの「Find inspiration in the style gallery」リンクを押下

- https://www.mapbox.com/gallery/ に遷移したら、「Mapbox Streets Japan」を選択する
　「explore →　」を押下
- mapが表示され、左下にある「Add Mapbox Streets Japan to your account」を押下
- 作成したアカウントで「https://studio.mapbox.com」　　遷移。東京駅辺りのマップが表示されます
- 画面右上メニューバーにある「share...」を押下
- share&develop 画面が表示され、Developer resources　の「StyleURL」と「Access token」を取得します
- <script>内で記載した以下の箇所を、上記で取得したStyleURLに書き換えます
 **変更前**
 ```
/* 地図styleID。YOLPではLayerSetIdに相当する。*/
style: 'mapbox://styles/mapbox/streets-v11',
 ```
  **変更後**
 ```
/* 地図styleID。YOLPではLayerSetIdに相当する。*/
style: 'mapbox://styles/mauilani/ckdba743a1c3k1imechwa99bh',
 ```
 - Access token は5番で設定した値と同じはず
 
 



 


# 概要
難解なことで有名なRakuten RMS Web APIのPHPのサンプル集です。
色んなAPIを叩いてRMSのデータを取得したり更新できるようになります。  

極力特別なパッケージは使用せず、デフォルトのPHPの機能で動作させる様に心がけています。
RMSを使ったツール開発のヒントになれば幸いです。

# 使い方
## config.phpを設定する

* config_sample.phpをconfig.phpにリネーム
* config.php内にAPIを使用するためのKey、店舗情報などを入力

## あとは下記APIごとのphpファイルをブラウザで開くとAPIのテストができます

# 商品API（ItemAPI）

## insertItem.php
item.insertのAPIを叩いて、ブラウザ上にリクエストと結果を表示  
下記を設定し、RMS店舗に商品を登録するサンプルです。  

* 商品名やURLなどの基本設定
* ディレクトリID、カタログID(JAN)の設定
* R-Cabinetにあげられてる画像を2枚設定
* ポイント変倍設定
* 送料など
* 納期管理番号の設定

## insertVariationItem.php
item.insertのAPIを叩いて、ブラウザ上にリクエストと結果を表示します  
在庫タイプ2：項目選択肢別在庫設定 を設定した際の新規商品登録のサンプルです。  
商品にカラーとサイズを設定して、バリエーションごとに個別に在庫を設定しています。
設定項目は下記。

* 商品名やURLなどの基本設定
* ディレクトリID、カタログID(JAN)の設定
* R-Cabinetにあげられてる画像を2枚設定
* ポイント変倍設定
* 送料など
* バリエーションの値設定（カラー×サイズ）
* バリエーションパターンごとに個別に在庫・画像設定

## updateItem.php
item.updateのAPIを叩いて、ブラウザ上にリクエストと結果を表示します  
下記を更新できることを確認しています。

* 商品名やURLなどの基本設定
* ディレクトリID、カタログID(JAN)の設定
* R-Cabinetにあげられてる画像を2枚設定
* ポイント変倍設定
* 送料など
* 納期管理番号の設定

## updateVariationItem.php
item.updateのAPIを叩いて、ブラウザ上にリクエストと結果を表示します  
在庫タイプ2：項目選択肢別在庫設定 を設定した際の新規商品登録のサンプルです。  
商品にカラーとサイズを設定して、バリエーションごとに個別に在庫を更新しています。  
※ 本APIではバリエーション単一で在庫更新はできません。必ず全てのバリエーションに対して在庫を設定して投げる必要があります。  
※ 一つだけバリエーションを設定して更新すると、他のバリエーションが消えます。  
※ バリエーション単一で更新する場合は在庫APIを使う必要があります  

* 商品名やURLなどの基本設定
* ディレクトリID、カタログID(JAN)の設定
* R-Cabinetにあげられてる画像を2枚設定
* ポイント変倍設定
* 送料など
* バリエーションの値設定（カラー×サイズ）
* バリエーションパターンごとに個別に在庫・画像設定


## getItem.php
item.getのAPIを叩いて、ブラウザ上にリクエストと結果を表示  
商品のitemUrlを指定して、その商品の情報を取得してくるサンプルです。  
RMS管理画面から色々情報設定して、その商品を取得すると、xmlがどういう構造になっているかわかりやすくていいです。  
表示されたxmlを下記にぶち込むと、整形してくれるので尚わかりやすい。    
http://tm-webtools.com/Tools/XMLBeauty

# R-CabinetAPI（CabinetAPI）

ドラフト作成。実動作不可。現在楽天に問い合わせ中。

# 受注API(OrderAPI)

## getOrder.php
getOrder APIを用いて、受注商品情報を取得する。  
処理の流れは
1. GetOrderRequestModelに取得したい受注の条件を記載
2. それをAPIコールする関数getOrder()に渡す

# 在庫API（InventoryAPI）(動きません)

## updateVariationInventory.php
在庫タイプが項目選択肢別在庫設定の場合の在庫を横軸縦軸単位で変更するAPIサンプル。
必須項目がないとかエラーが出て動作してません。  （なんの必須項目かぐらい出してくれ楽天）

## getInventoryExternal.php
商品URLを指定して在庫を取得するAPIサンプル。  
検索エラーが発生しましたと言うエラーが出て動作してません。(コード表を見ると「時間を空けて再度お試しください」と書いてある。嘘をつけ)


# 決済API

coming soon...
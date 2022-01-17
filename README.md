# sample-webapp

Webアプリケーションの仕組みを理解する目的で作られたネットショップです。Pythonで実装されています。

## セットアップ方法

Python3.9で動作確認しています。必要な外部ライブラリはいまのところ[Bottle](https://bottlepy.org/docs/dev/) だけです。以下の方法でインストールできます。

```
pip install -r requirements.txt
```

Bootstrapに準拠したCSSフレームワークであるHonokaが必要です。[こちら](https://github.com/windyakin/Honoka/releases/download/v4.4.1/bootstrap-honoka-4.4.1-dist.zip) からダウンロードしてapp.pyがあるディレクトリにhonokaという名前で展開してください。通常そのままzipファイルを解凍するとhonokaディレクトリになります。

## 起動方法

以下のコマンドで起動します。

```
python3 app.py
```

ローカルホストのポート5000番でサーバが起動します。Webブラウザを起動し、以下のURLをアドレスに入力してください。お客さんが利用することを想定したページが表示されます。

```
http://localhost:5000/
```

管理業務には目的に応じて以下のパスを指定してください。

|  パス  |  説明  |
| ---- | ---- |
|  /admin/order  | 注文を管理するページ  |
|  /admin/stock  |  在庫を管理するページ  |    

## 基本的な機能

お客さんは、商品を選んで個数を指定し購入をクリックします。カート機能は無いので、商品は1つだけしか選べません。次の画面で名前、メールアドレス、発送先を指定し注文を確定します。

注文が入ると、注文管理ページで確認できます。この時点で在庫が減っています。出荷処理が済んだら、注文の状態を出荷済みにします。注文をキャンセルするとその分の在庫が戻ります。

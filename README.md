# git clone してからのコマンド

### クローン先のディレクトリに移動して以下のコマンドでコンテナを構築

`docker-compose up -d`

### アクセスして確認

デフォルトではポートを 8080 に設定しているので以下でアクセス<br>
HTTPSの場合 [http://localhost:8080](http://localhost:8080) <br>
HTTPSの場合 [https://localhost:8080](https://localhost:8080) 

## 注意点

web サーバでアクセスせずに、file:///C:/ で開発を行っている場合は json ファイルを読み込むことができないので、web サーバでアクセスすること。<br>
そうしないと**CORS(クロスオリジン)エラー**が発生して json ファイルを取得することができない。以下のようなエラーがコンソールに出る。<br>

![crossOriginError の写真](https://github.com/systemac-jp/map-app/tree/main/server/img/crossOriginError.png)

## CORS(クロスオリジン)エラー参考記事

[CORS エラー対策](https://qiita.com/ta-ke-no-bu/items/b7cd4b4719249a9c365e)
[CORS(クロスオリジン)エラーを無視するためのブラウザ設定](https://webbibouroku.com/Blog/Article/cors-browser-setting)

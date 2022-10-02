# README

* YoutubeチャンネルのFarstep様の動画を参考にして作成したTodoListです。
* Reactの勉強用です。
## 個人的躓いた点
* CSRFのトークン認証ができていないというエラー
``` console
Can't verify CSRF token authenticity.
Completed 422 Unprocessable Entity in 22 ms
```
解決方法
``` /app/controller/application_controller.rb
# /app/controller/application_controller.rb
+ protect_from_forgery with: :null_session
```
CSRF対策が「例外の発生」から「セッションのクリア」になる
セッションのクリアのとき処理は継続されるためAPIのエンドポイントを叩いたら結果が返ってくるようになる
* react-router-dom V6~ 仕様が変わっている点　（例：　withRouterが使えなかった）
* Todoの更新や新規作成時に指定のページにリダイレクトされなかった　（withRouterを使うことで解決）
* 解決したが原因がわからないエラー
``` console
Can't find the named export '***' from non EcmaScript module
```
解決方法　　
package.jsonファイルからwebpack, webpack-ciを削除, react-toastifyのバージョンを変更

## 参照
* Farstep様　Youtubeチャンネル　（https://www.youtube.com/channel/UCiGdng-6ZLS5tlfw0xnG3TA）

# MyJobHuntingNote  

## URL
http://tt-707.99sv-coco.com/mission_6-login.php  
※ブラウザは「GoogleChrome」推奨。  
※ログイン（サインアップ）しないと利用不可。

## 概要
「就活生向けの活動管理サイト」  

1. 活動記録まとめ（Activity）  
2. 企業研究まとめ（Company Note）
3. 履歴書用メモ（Resume）  
4. スケジュール管理用カレンダー（Schedule）  

の４つの機能が利用可能。  
（以下、各機能ページの概要）  


#### 1. 活動記録まとめ（Activity）  
ブログ形式で活動記録を保存できる。  
カテゴリ/投稿月ごとに、参照可能（カテゴリは自由に新規作成可能）。  

#### 2. 企業研究まとめ（Company Note）  
各企業毎に、研究内容を保存できる。  
編集・削除可能。  

#### 3. 履歴書用メモ（Resume）  
企業研究と同様に、履歴書用メモを保存可能。  
編集可能。  
画像（写真）アップロード可能。  

#### 4. スケジュール管理用カレンダー（Schedule）  
標準的なカレンダーと同様に、予定を書き込める。  
参照月の予定をカレンダー下に表示。  
予定は色分け可能。  
編集・削除可能。  


## 各種ページ（phpファイル）について  

※コード参照する際は、タブ幅=2推奨（URLの末尾に 'ts=2'）

### ● ログイン・新規登録  

【login.php】  
・ログインと新規登録をするページ  
・ログインは名前・メール・パスワードを入力してもらい、  
　それをデータベースと照らし合わせ、あっていればログイン。  
・新規登録はメールアドレスだけ入力してもらい、  
　そのアドレスに新規登録用ページ（signup.php）へのリンクを送信する  
・「forgot password?」を押すと、パスワードを忘れた人用のページ「forgotpw.php」に飛ぶ  


【signup.php】  
・新規登録用のページ  
・名前とパスワードを入力してもらい、それをデータベースに保存し、  
　ユーザ情報ページ（config.php）にとばす  


【forgotpw.php】  
・パスワードを忘れた人用のページ  
・名前とメールアドレスを入力してもらい、  
　そのアドレスにパスワード変更用ページ「changemlpw.php」のリンクを送信  


【changemlpw.php】  
・メールアドレス変更・パスワード変更用のページ  
・メールアドレス変更の場合、認証のみ。  
　成功したらログインページ「login.php」へのリンクを表示  
・パスワード変更の場合、新しいパスワードを入力してもらう。  
　変更に成功したらログインページ「login.php」へのリンクを表示  




### ● 設定ページ（User Info）  

【config.php】メニューバーあり  
・ユーザ情報を表示するページ  
・名前・メアド・パスワードの変更ボタン、ログアウト・ユーザ削除ボタンがある  
　・名前変更はこのページのみで完結  
　・メアド・パスワード変更はメールで「changemlpw.php」へ飛ばして行う  
　・ログアウトボタンは、ログインページ「login.php」へとばす  
　・ユーザ削除ボタンは、文字通りユーザ情報を削除する  




### ● カレンダー（Schedule）  

【schedule.php】メニューバーあり  
・「カレンダー」と「表示している月の予定」を表示するページ  
「カレンダー」  
　・「<<」「>>」ボタンは前月/次月に移動する  
　・日付はボタンになっていて、押すとその日のページ「event.php」に飛ぶ  
　・予定が入っていると、各日のセルに予定タイトルのラベルが表示される。  
　（そのラベルもボタン → 予定編集ページ「editevent.php」に飛ぶ）  
「表示している月の予定」  
　・予定が入ってると、予定のタイトル・詳細・編集ボタン・削除ボタンが表示される  
　　（編集ボタン → 予定編集ページ「editevent.php」に飛ぶ  
　　　削除ボタン → その予定が削除される）  
　・日付はボタンになっていて、表示/非表示を切り替えられる  

【event.php】  
・指定日の予定を表示・追加を行うページ  
・「予定表示」「予定追加」はボタンになっていて表示/非表示の切り替えができる  
・HOMEボタンは「schedule.php」に飛ぶ  

【editevent.php】  
・指定した予定の編集を行うページ  
・BACKボタンは、その予定の日の「event.php」に飛ぶ  
・HOMEボタンは「schedule.php」に飛ぶ  


### ● 企業情報まとめページ（Company Note）  

【conote.php】  
・企業情報やその企業への自分のメモなどを保存可能  
・追加・削除・編集が可能  

【editconote.php】  
・登録した企業情報の編集をするページ。  


### ● 履歴書メモページ（Resume）  

【resume.php】  
・履歴書に書く項目をメモしておくページ  
・写真もアップロード可能  


### ● 活動記録ページ（Activity）  

【activity.php】  
・ブログ形式で活動記録を保存できる  
・メインとサイドバーで画面２分割  
・月別・カテゴリー別にも表示可能  


### ● CSS  

【sign.css】  
login.php  
signup.php  
forgotpw.php  
のデザインを設定しているcssファイル  


【design.css】  
上記３つ以外のデザインの設定をしているcssファイル  

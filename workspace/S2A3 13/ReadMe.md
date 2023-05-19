# データベース応用 実習ワークスペース

## VSCode に最初にインストールする 拡張機能

### 入れ方

1. 左の「拡張機能」ボタンを押す
1. 検索ボックスに「@recommended」を入れる
1. 「ワークスペースの推奨事項」に表示されている Extension をインストール

### 対象

- Japanese Language Pack for Visual Studio Code
- Prettier
- Prettier SQL VSCode
- Tabnine
- Better Comments
- indent-rainbow
- vscode-icons

## 実習ワークスペース フォルダ構成

- 0.env
  - DB の初期化 SQL を格納している
- 1.text
  - 教科書の実習 SQL を作成する
- 2.task
  - 演習問題の SQL を作成する

## Docker 実習環境の準備手順

### Docker コンテナの起動

1. VirtualBox の仮想アプライアンスファイル「DB-Server.ova」をデスクトップにコピーする

- 「DB-Server.ova」は、「パブリックのドキュメント」または、「USB」から入手

2. 「DB-Server.ova」をインポート

- [ファイル]→[仮想アプライアンスのインポート]→ ファイルに「DB-Server.ova」を指定して[次へ]→[完了]

3. ネットワークの確認

- DB-Server を選択して、[設定]→[ネットワーク]を確認

4. VirtualBox マネージャーからダブルクリックで起動する

- ※エラーになった場合は、サーバーを除去して再度インポート

5.  ログイン

- ユーザー：root
- パスワード：alp001

6. コマンド実行

- `./start`

7. IP アドレスの確認｜「192.168」で始まる IP を確認する

- `ip a | grep 192.168`

### DBViewer(pgAdmin4)へ接続

1. ブラウザで pgAdmin にアクセスし、ログイン

- http://192.168.x.x:5500/ ← x は 3-(6)で確認した値
  - email : example@example.com
  - pass : passw0rd

2. DB サーバに接続する

- 「Servers」→「db」

  - password : postgres
  - ※パスワードは「Save Password」で保存

    3.DB 内容を確認する

- 「Databases」→「appdb」→「Schemas」→「public」→「Tables」

  - 各テーブルを右クリック →「View/Edit Data」→「All Rows」

    4.SQL を実行してみる

- 「Tables」を右クリック →「Query Tool」
- SQL を入力し、「▶」で実行する
  - `SELECT \* FROM dept;`
  - SQL の実行結果が表示されること

### 実習を終了する場合

1. 実行中の VirtualBox ウィンドウを右上の「✕」で閉じる
1. 「仮想マシンの状態を保存」にチェックが入っていることを確認し、「OK」

- 少し時間が経つと安全に終了し、ウィンドウが閉じられる

**次回起動時に状態が復旧されます**

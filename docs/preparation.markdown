# 作業準備

この章では、ハンズオンの準備を説明しています。以下の手順に従い環境を整えてください。

## 前提条件

- python 3.12 のインストールと`python.exe`が存在しているフォルダパスが環境変数 PATH に設定されていること。
- pip が使える環境であること
- [git for windows](https://gitforwindows.org/) がインストール済みであること

## Visual Studio Code を起動する

### 起動

1. Windows キー -> `visual`とタイプ
1. `Visual Studio Code`のアイコンを押下

![Visual Studio Code を起動する](./images/launch-vscode.png)

## GitHub Clone する

1. [Git リポジトリをブラウザで開く](https://github.com/tsukashusan/assistants-api-sample-using-python)

1. リポジトリの URL を取得する。クリップボードにコピー
   ![alt text](./images/git-get-repository-url.png)

1. Visual Studio で `Ctrl + Shift + g` をタイプし、ソース管理を表示

1. `リポジトリの複製` または `Git リポジトリのクローン` をクリック
   ![alt text](./images/git-clone-open.png)

1. クリップボードにコピーされている URL を入力して「Enter」
   ![alt text](./images/git-get-repository-url-enter.png)

1. フォルダ選択ダイアログが表示されるので、任意の`空のフォルダ`を選択する</br>※**空ではないフォルダを選択した場合、正常に動作しません**
   ![alt text](./images/git-get-repository-choice-folder.png)

1. クローンが始まると、図のように、右下にプログレスバーが表示される
   ![alt text](./images/git-get-repository-clone-in-progress.png)

1. 完了するとダイアログが表示され、`開く` または　`新しいウィンドウで開く` を押下
   ![alt text](./images/git-get-repository-open-folder.png)

1. 「このフォルダー内のファイルの作者を信頼しますか?」とダイアログが表示されるので、`フォルダーを信頼して続行`を押下
   ![alt text](./images/git-get-repository-trust-folder.png)

1. さらに以下のようなメッセージダイアログが表示された場合も、`はい、作成者を信頼します`を押下</br>※「**親フォルダー...内のすべてのファイルの作成者を信頼しますのチェックは任意**」
   ![alt text](./images/git-get-repository-trust-author.png)

1. git clone の完了
   ![alt text](./images/git-get-repository-complete-clone.png)

## terminal の立ち上げ

1. `ctrl + shift + p`を入力

1. コマンド入力フィールドに`terminal: create new terminal`と入力

1. `Terminal: Create New Terminal (In Active Workspace)` を選択
   ![alt text](./images/terminal-new.png)

1. 図のように、ターミナルウィンドウが Visual Studio の下部に出力される (PowerShell の場合)
   ![alt text](./images/terminal-complete-powershell.png)

1. または図のように、ターミナルウィンドウが Visual Studio の下部に出力される (Command Prompt の場合)
   ![alt text](./images/terminal-complete-cmd.png)

## virtualenv が未インストールの方

個別の環境構築のため、Python の仮想環境を作成します。

```
pip install virtualenv
```

## virtualenv を使って仮想環境を作成

```
python -m virtualenv -p  python3.12 extension-lectures
```

## Set-ExecutionPolicy による PowerShell の実行ポリシーの変更 (ターミナルが PowerShell の場合)

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Bypass -Force
```

## アクティベート (ターミナルが PowerShell の場合)

```
.\extension-lectures\Scripts\activate.ps1
```

## アクティベート (ターミナルが Command Prompt の場合)

```
.\extension-lectures\Scripts\activate.bat
```

## パッケージのインストール

Python を実行するにあたり、

```
pip install -r requirements.txt
```

## Visual Studio Code の拡張機能

### CTRL+SHIFT+X または 拡張機能をクリック

### Python 拡張のインストール

【インストール】を押下
![Python拡張のインストール](./images/extension-python.png)

### Jupyter 拡張のインストール

【インストール】を押下
![Jupyter拡張のインストール](./images/extension-jupyter.png)

### インストール中

![インストール中](images/extension-install.png)

### インストール完了

インストール後、Visual Studio Code を再起動する。
【インストール】が消えていればインストール完了。
![インストール完了](images/extension-python-complete.png)

### REST Client 拡張のインストール

【インストール】を押下
![REST Client 拡張のインストール](./images/extension-REST-API.png)

### インストール完了

【インストール】が消えていればインストール完了
![インストール完了](./images/extension-REST-API-completed.png)

### Markdown preview mermaid 拡張のインストール

【インストール】を押下
![Markdown preview mermaid 拡張のインストール](./images/extension-mermaid.png)

### インストール完了

【インストール】が消えていればインストール完了
![Markdown preview mermaid 拡張のインストール完了](./images/extension-mermaid-completed.png)

## Azure OpenAI Studio を使って、gpt-4o のモデルをデプロイ

### Azure OpenAI Studio へアクセス

![Azure OpenAI Studioへ移動](./images/move-openai-studio.png)

### 【新しいエクスペリエンスを探索する】を押下

![新しいエクスペリエンスを探索する](./images/new-experience.png)

### モデルのデプロイ

![＋モデルのデプロイを押下](./images/modeldeploy-1.png)

### 基本モデルをデプロイする

![基本モデルをデプロイ](./images/modeldeploy-2.png)

### gpt-4o を選択し、【確認】を押下

![alt text](./images/selection-gpt4-o.png)

### 【グローバル標準】を選択

![alt text](images/selection-global.png)

### トークンレート制限を 450K に設定し、【デプロイ】を押下

![alt text](images/token-rate-450K.png)

### 作成したモデルのモデル名(gpt-4o)をクリップボードにコピーし、.env の AZURE_OPENAI_MODEL_NAME の値として貼り付ける

![alt text](images/model-name.png)

## `.env` を編集

### Azure Portal から「キー 1 の値」と「エンドポイントの URL」貼り付ける。また、作成したモデル名(**gpt-4o**)を貼りつける

※GET_WEATHER_URL は別の工程で値を追記</br>
※※各文字列を二重引用符(ダブルクォーテーション)で囲むことは不要

![キー1](images/key-endpoint.png)

```python:.env
AZURE_OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 「キー1の値」
AZURE_OPENAI_ENDPOINT=https://xxxx-xxxx-xxxx.openai.azure.com/「エンドポイントURL」
AZURE_OPENAI_MODEL_NAME=gpt-4o 「モデル名」
GET_WEATHER_URL=
```

## ハンズオンの開始

準備が完了したので、
[assistants-api.ipynb](../assistants-api.ipynb)へ移動

[README に戻る](../README.markdown)

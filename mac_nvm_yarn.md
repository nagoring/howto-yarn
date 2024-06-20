# Yarnとnvmを使用したセットアップ手順 (Mac版)

## 1. nvmのインストール
1. ターミナルを開き、nvmのインストールスクリプトをダウンロードして実行：
    ```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
    ```
2. `~/.zshrc`ファイルに以下を追加し、nvmの設定を完了：
    ```bash
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
    ```
3. 設定を反映させるため、ターミナルを再起動するか以下のコマンドを実行：
    ```bash
    source ~/.zshrc
    ```

## 2. Node.jsのインストールとバージョンの設定
1. nvmのインストールを確認：
    ```bash
    nvm -v
    ```
2. Node.jsのインストール：
    ```bash
    nvm install --lts
    ```
3. Node.jsの使用バージョンを設定：
    ```bash
    nvm use --lts
    # または特定のバージョンを指定
    nvm install 20
    nvm use 20
    ```

## 3. Yarnのインストール
1. Yarnのインストール：
    ```bash
    npm install -g yarn
    ```
2. Yarnのバージョン確認：
    ```bash
    yarn -v
    ```

## 4. Yarnの設定ファイルを編集
1. ユーザーディレクトリに移動：
    ```bash
    cd ~
    ```
2. `.yarnrc.yml`ファイルの作成：
    ```yaml
    globalFolder: "/Users/your_username/.yarn-global"
    cacheFolder: "/Users/your_username/.yarn-cache"
    nodeLinker: "pnp"
    ```
## 5. プロジェクトのセットアップ (続き)
1. プロジェクトディレクトリの作成と移動：
    ```bash
    mkdir ~/my_project
    cd ~/my_project
    ```
2. Yarnのバージョンを設定：
    ```bash
    yarn set version berry
    ```
3. プロジェクトの初期化：
    ```bash
    yarn init -y
    ```
4. 依存関係のインストール：
    ```bash
    yarn add lodash
    ```
5. プロジェクト内のディレクトリ構成の確認：
    ```bash
    ls
    ```
    プロジェクトディレクトリ内に`package.json`と`.yarn`ディレクトリが作成されていることを確認します。

6. `yarn.lock`ファイルの生成：
    ```bash
    yarn install
    ```
    これにより、依存関係が解決され、`yarn.lock`ファイルが生成されます。

## 6. 開発の基本操作
1. 開発サーバーの起動（適切なスクリプトが`package.json`に定義されている場合）：
    ```bash
    yarn start
    ```
2. テストの実行：
    ```bash
    yarn test
    ```
3. ビルドの実行：
    ```bash
    yarn build
    ```

## 7. 依存関係の管理
1. 新しいパッケージの追加：
    ```bash
    yarn add <package-name>
    ```
2. 開発依存パッケージの追加：
    ```bash
    yarn add --dev <package-name>
    ```
3. パッケージの削除：
    ```bash
    yarn remove <package-name>
    ```
4. 全依存関係の更新：
    ```bash
    yarn upgrade
    ```

## 8. トラブルシューティング
1. Node.jsのバージョンを確認し、適切なバージョンを使用しているか確認：
    ```bash
    node -v
    ```
2. Yarnのキャッシュをクリアする：
    ```bash
    yarn cache clean
    ```
3. nvmでNode.jsのバージョンを変更する：
    ```bash
    nvm use <version>
    ```

## 9. 便利なコマンド
1. 使用中の全パッケージとそのバージョンを表示：
    ```bash
    yarn list
    ```
2. スクリプトの実行（`package.json`に定義されたスクリプト）：
    ```bash
    yarn run <script-name>
    ```
3. パッケージの情報を表示：
    ```bash
    yarn info <package-name>
    ```


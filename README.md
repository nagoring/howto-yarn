# Yarnとnvmを使用したセットアップ手順

## 1. nvmのインストール
1. [nvm-windowsの公式ページ](https://github.com/coreybutler/nvm-windows/releases)にアクセスし、最新のリリースをダウンロード。
2. ダウンロードしたインストーラーを実行し、nvmをインストール。

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
    or
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
    cd %USERPROFILE%
    ```
2. `.yarnrc.yml`ファイルの作成：
    ```yaml
    globalFolder: "E:\\yarn-global"
    cacheFolder: "E:\\yarn-cache"
    nodeLinker: "pnp"
    ```

## 5. プロジェクトのセットアップ
1. プロジェクトディレクトリの作成と移動：
    ```bash
    mkdir E:\my_project
    cd E:\my_project
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

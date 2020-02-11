# simple-sample

## 概要

最小構成のNodeスクリプトです。指定したMACアドレスにscan&connectをかけにいき、接続後データ取得を開始します。

## Prerequisites 必要な外部パッケージ

事前に以下のパッケージを組み込んでください。標準ではnoble-winrtがpackage.jsonで設定されています。

- noble派生のいずれかを読み込み
    - noble-uwp(https://github.com/jasongin/noble-uwp)
        - Windows(Windows 10 build 10.0.15063 or later)のBLEライブラリ
        - MIT License
        - ^0.6.2
        - npm経由だと異なるものがインストールされるのでgithub経由でインストールしてください
- jinsmemesdk-node-noble-x
    - JINS MEME SDK 部分です。
    - License: [JINS MEME SDK 利用規約(ja)](https://developers.jins.com/ja/sdks/terms_and_conditions/) [(en)](https://developers.jins.com/en/sdks/terms_and_conditions/)
    - ^0.12.2

## Sample使用手順

1. git clone したあと、simple-sample/meme_sample.js の以下のnoble指定個所を必要に応じて修正してください
    - Windows 10: `module.exports.noble_type = 'noble-uwp';`
1. package.json の dependencies も noble-uwpに修正
1. npm install　noble-uwp@latest
1. npm install jinsmemesdk-node-noble-x@latest
1. meme_sample.js内のアプリ認証(app_id/app_secret)情報、接続するMEMEのMACアドレス(mac_addr_to_connect, **コロンなし小文字** )を記載
1. binding.nodeが無いとエラーが出た場合はリビルド rebuild if there is no 'binding.node' `npm rebuild --build_from_source=true`
1. `node meme_sample.js`

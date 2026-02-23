# CCaslII_DockerImage
CCaslII(Linux板)のDockerイメージです。完全に自分用です。

Docker Hubのリンクはこちら

[https://hub.docker.com/r/mendoitarou/ccasl2](https://hub.docker.com/r/mendoitarou/ccasl2)

## CCaslIIについて
(本家`readme.txt`より抜粋)
CCaslIIは，情報処理技術者試験の仮想コンピュータ「COMETII」，そのアセンブラ言語「CASLII」のシミュレータです。

詳しくは[readme.txt](./src/ccasl2-4.10/readme.txt)を参照してください。

### 注意事項
1. 本ソフトウェアの著作権は、著作者である山口秀昭にあります。
2. 本ソフトウェアのコピー、転載は自由です。ただし、雑誌、書籍等に転載する場合は、メールにてご一報ください。

**このDockerイメージはソフトウェアのコピーおよび転載と認識しています。**

## イメージの使い方(CCaslIIの使い方は除く)
Dockerがインストール済みの環境を想定しています。

下記のコマンドで、イメージをダウンロードして、コンテナ内でbashを起動します。

```bash
$ docker pull mendoitarou/ccasl2:latest
$ docker run mendoitarou/ccasl2:latest /bin/bash
```

コンテナ内で、以下のコマンドを実行し正しく動作するか確認してください。

```bash
$ caslasm -h
```

ヘルプが表示されれば、イメージの利用準備は完了です。

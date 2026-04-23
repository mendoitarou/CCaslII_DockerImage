# CCaslII_DockerImage
CCaslII(Linux板)のDockerイメージです。完全に自分用です。

Docker Hubのリンクはこちら

[https://hub.docker.com/r/mendoitarou/ccasl2](https://hub.docker.com/r/mendoitarou/ccasl2)

## CCaslIIについて
本家のホームページは[こちら](https://hyamag.sakura.ne.jp/hysoft/ccasl2_linux/)

(本家`readme.txt`より抜粋)
CCaslIIは，情報処理技術者試験の仮想コンピュータ「COMETII」，そのアセンブラ言語「CASLII」のシミュレータです。

詳しくは[readme.txt](./src/ccasl2-4.10/readme.txt)を参照してください。

### 注意事項
1. 本ソフトウェアの著作権は、著作者である山口秀昭にあります。
2. 本ソフトウェアのコピー、転載は自由です。ただし、雑誌、書籍等に転載する場合は、メールにてご一報ください。

**このDockerイメージはソフトウェアのコピーおよび転載と認識しています。**

## イメージの使い方(CCaslIIの使い方は除く)
Dockerがインストール済みの環境を想定しています。

プログラムをホストで書いて、コンパイル・実行だけをコンテナで行う環境を構築してみます。

ホストでディレクトリを作り、その中に`src`というディレクトリを作ります。そこにプログラムを書いていきます。

```shell
❯ tree
.
└── src
    └── test.cas

2 directories, 1 file
```

こんな感じです。

このディレクトリで以下のコマンドを実行すると、`/src`がマウントされたコンテナが立ち上がります。

(`CCaslII`という名前で、コンテナ内のbashに入ります。なお、`--rm`オプションを付けているので、bashから出ると自動でコンテナは削除されます。)

```shell
docker run --name CCaslII --rm -v ./src:/src/ -it mendoitarou/ccasl2:latest /bin/bash
```

あとは、コンテナの中で`/src`に移動し、コンパイル・実行をすればOKです。

実行例:

```shell
❯ docker run --name CCaslII --rm -v ./src:/src/ -it mendoitarou/ccasl2:latest /bin/bash
root@c169c9250f91:/# ls /src
test.cas
```

makeを使いたい人は、コンテナに入って追加でインストールしてください。(もしかしたら、別タグでmakeインストール済みのものを用意するかもしれません。)

```
apt update && apt install make
```

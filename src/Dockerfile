# Ubuntuベース
FROM ubuntu:latest

# CCaslIIをコピー
COPY ./ccasl2-4.10/casl* /usr/local/bin/

# 32bit環境のインストール
RUN apt update
RUN apt install lib32z1 lib32stdc++6 -y

# キャッシュ削除
RUN apt clean

# Bashの実行
CMD ["/bin/bash"]

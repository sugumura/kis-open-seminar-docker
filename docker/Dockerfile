# ベースとなるイメージ名
FROM php:7-cli-alpine

# 環境変数の宣言
ENV PUBLIC_DIR /public

# CMDを実行する作業ディレクトリを指定
WORKDIR $PUBLIC_DIR

# ビルドするホストからイメージにファイルをコピー
COPY . $PUBLIC_DIR

# 使用するポートを宣言
EXPOSE 8080

# コンテナで実行するコマンド
CMD [ "php", "-S", "0.0.0.0:8080" ]

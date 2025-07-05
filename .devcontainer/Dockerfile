# ベースイメージ
FROM mcr.microsoft.com/devcontainers/base:debian

# 必要なパッケージインストール
RUN apt-get update && \
    apt-get install -y imagemagick && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

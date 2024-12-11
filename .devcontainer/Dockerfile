FROM ubuntu:22.04

# 基本的なツールとPythonのインストール
RUN apt-get update && apt-get install -y \
    postgresql-client \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

# デフォルトのPythonをpython3に設定
RUN ln -s /usr/bin/python3 /usr/bin/python

# 作業ディレクトリの設定
WORKDIR /workspaces

# 非rootユーザーの作成
RUN useradd -m -s /bin/bash vscode \
    && chown -R vscode:vscode /workspaces

# ユーザーの切り替え
USER vscode

CMD ["/bin/bash"]
FROM mcr.microsoft.com/devcontainers/base:jammy

# install packages
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y curl
RUN rm -rf /var/lib/apt/lists/*

# install pax
RUN mkdir --parents /home/vscode/.local/bin
RUN curl -s https://api.github.com/repos/froehlichA/pax/releases/latest | \
    jq -r '.assets[] | select(.name=="pax") | .browser_download_url' | \
    wget --no-verbose --output-document=/home/vscode/.local/bin/pax --input-file=-
RUN chmod +x /home/vscode/.local/bin/pax
RUN chown --recursive --changes vscode:vscode /home/vscode/.local

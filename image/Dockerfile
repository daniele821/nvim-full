FROM fedora

# install needed packages
RUN dnf install -y lsd ripgrep bat git bash-completion htop bat jq zoxide \
    neovim git unzip wget ripgrep tree-sitter-cli nodejs npm python3 golang && \
    dnf autoremove -y && dnf clean all

# initialize neovim and bash
RUN git clone --depth 1 https://github.com/daniele821/nvim-full /root/.config/nvim && \
    go telemetry off && nvim --headless +StarterPack +qa && rm -rf /root/.cache /root/.npm /root/go && \
    cp /root/.config/nvim/image/bashrc /root/.bashrc && cp /root/.config/nvim/image/gitconfig /root/.gitconfig

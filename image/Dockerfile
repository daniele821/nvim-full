FROM fedora

# install needed packages
RUN dnf install -y --setopt=install_weak_deps=False lsd ripgrep bat git bash-completion htop bat jq zoxide \
    neovim git unzip wget ripgrep tree-sitter-cli nodejs npm python3 gcc && \
    dnf autoremove -y && dnf clean all

# initialize neovim and bash
RUN git clone --depth 1 https://daniele821@github.com/daniele821/nvim-full.git /root/.config/nvim && \
    git -C /root/.config/nvim remote set-url origin --add https://daniele821@gitlab.com/daniele821/nvim-full.git && \
    git -C /root/.config/nvim config user.name "Daniele Muffato" && git -C /root/.config/nvim config user.email "danixgithub1@gmail.com" && \
    nvim --headless +StarterPack +qa && rm -rf /root/.cache /root/.npm && \
    cp /root/.config/nvim/image/bashrc /root/.bashrc && cp /root/.config/nvim/image/gitconfig /root/.gitconfig

# add /data volume
VOLUME /data

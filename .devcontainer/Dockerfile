FROM mcr.microsoft.com/vscode/devcontainers/go:0-1.17-bullseye

ARG CUE_VERSION=v0.4.1

RUN curl -sL https://github.com/cue-lang/cue/releases/download/${CUE_VERSION}/cue_${CUE_VERSION}_linux_$(dpkg --print-architecture).tar.gz \
    | tar -xz -C /usr/local/bin cue

ENV SHELL=/bin/zsh \
    ZSH_CUSTOM=/root/.oh-my-zsh/custom

RUN mkdir /root/.oh-my-zsh/custom/plugins/cue \
    && cue completion zsh > ${ZSH_CUSTOM}/plugins/cue/_cue

COPY .zshrc /root/.zshrc

RUN git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM}/plugins/zsh-autosuggestions
RUN git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM}/plugins/zsh-syntax-highlighting

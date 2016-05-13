FROM phusion/baseimage

RUN apt-get update && \
    apt-get install -y git zsh tmux vim  && \
    rm -f /etc/service/sshd/down && \
    /etc/my_init.d/00_regen_ssh_host_keys.sh && \

    #oh-my-zsh and dotfiles
    chsh -s /bin/zsh && \
    git clone https://github.com/zet235/dotfiles.git ~/.dotfiles


EXPOSE 22 80

FROM phusion/baseimage:0.9.17

# fix ERROR: invoke-rc.d: policy-rc.d denied execution of start.
RUN apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get install -y zsh vim git gcc-multilib man tmux nginx ipython bpython wget python2.7 python-pip  python2.7-dev dialog strace ltrace  && \
    apt-get install -y libssl-dev libffi-dev g++-4.8-multilib  && \
    #install gdb
    apt-get install -y gdb nasm  && \
    #install ncat
    apt-get install -y netcat-traditional netcat-openbsd nmap && \

    #pwntools
    pip install --upgrade pip && \
    pip install git+https://github.com/Gallopsled/pwntools#egg=pwntools && \
    #pip install --upgrade capstone && \

    #ssh
    rm -f /etc/service/sshd/down && \
    /etc/my_init.d/00_regen_ssh_host_keys.sh && \

    #dotfiles
    chsh -s /bin/zsh && \
    git clone https://github.com/zet235/dotfiles.git ~/.dotfiles && \

    #ctf tools
    git clone --recursive https://github.com/zet235/ctf-tools.git ~/.ctf-tools && \
    #clean up
    apt-get autoclean && apt-get clean && apt-get autoremove



EXPOSE 22 80 3002 3003

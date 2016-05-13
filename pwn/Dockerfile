FROM phusion/baseimage

# fix ERROR: invoke-rc.d: policy-rc.d denied execution of start.
RUN sed -i 's/exit 101/exit 0/g' /usr/sbin/policy-rc.d && \
    apt-get update && \
    #apt-get dist-upgrade -y && \
    apt-get install -y zsh vim git gcc-multilib man tmux nginx ipython bpython wget python-pip python-dev dialog strace ltrace && \
    #install gdb
    apt-get install -y gdb libc6-dbg nasm micro-inetd && \
    #install ncat
    apt-get install -y netcat-traditional netcat-openbsd nmap && \
    #install pwntools
    pip install --upgrade pip && \
    pip install git+https://github.com/Gallopsled/pwntools#egg=pwntools && \
    pip install --upgrade capstone && \
    pip install pycrypto ecdsa gevent && \

    #ssh
    rm -f /etc/service/sshd/down && \
    /etc/my_init.d/00_regen_ssh_host_keys.sh && \

    #dotfiles
    chsh -s /bin/zsh && \
    git clone https://github.com/zet235/dotfiles.git ~/.dotfiles && \

    #clean up
    apt-get autoclean && apt-get clean && apt-get autoremove



EXPOSE 22 80 3002 3003

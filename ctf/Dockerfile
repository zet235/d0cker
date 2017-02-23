FROM phusion/baseimage:0.9.17

RUN apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get install -y zsh vim git gcc-multilib man tmux ipython bpython wget python2.7 python-pip  python2.7-dev strace ltrace  && \
    apt-get install -y libssl-dev libffi-dev g++-4.8-multilib  && \
    #install gdb
    apt-get install -y gdb nasm  && \
    #install ncat
    apt-get install -y netcat-traditional netcat-openbsd nmap && \

    #pwntools
    apt-get -y install python2.7 python-pip python-dev git libssl-dev libffi-dev build-essential && \
    pip install --upgrade pip && \
    pip install appdirs && \
    pip install --upgrade pwntools && \

    #ssh
    rm -f /etc/service/sshd/down && \
    /etc/my_init.d/00_regen_ssh_host_keys.sh && \
    
    chsh -s /bin/zsh


EXPOSE 22 3002 3003

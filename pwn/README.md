# pwn-box

* 用 docker 打造一個打pwn的環境
* 還沒開始使用 docker hub

##How to use

```bash
git clone https://github.com/zet235/pwn-box.git && cd pwn-box
cd pwn && docker build -t zet235/pwn-box .
```

* 運行方式

        docker run --name pwn \
            -h pwn \
            -it --privileged \
            -v /etc/localtime:/etc/localtime:ro \
            -p 3002:3002 -p 3003:3003 \
            zet235/pwn-box /bin/bash
    or

        docker run --name pwn -d \
            -h pwn \
            --privileged \
            -v /etc/localtime:/etc/localtime:ro \
            -p 3002:3002 -p 3003:3003 -p 81:80 -p 3333:22 \
            --restart=always \
            zet235/pwn-box

* 可以使用docker exec 來修改root密碼

        docker exec -i -t container_id bash

* 假如想保持容器運行可以

        先按 ctrl+p
        再按 ctrl+q

* 取回容器

        docker attach pwn


# pwn-box

> 用 docker 打造一個打ctf的環境

## How to use


* 運行方式

```
docker run --name u16 -d \
    -h ubuntu \
    --privileged \
    -v /etc/localtime:/etc/localtime:ro \
    -p 3002:3002 -p 3003:3003 -p 3333:22 \
    --restart=always \
    zet235/ctf
```

* 可以使用docker exec 來修改root密碼

        docker exec -it container_id bash

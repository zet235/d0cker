
## webui-aria2

```
sudo docker build -t yourname/webui-aria2 .
```

..and run it! It will be available at: http://localhost:9100

```
sudo docker run --restart=always -d -v /Downloads:/data -p 6800:6800 -p 9100:8080 --name="webui-aria2" yourname/webui-aria2
```

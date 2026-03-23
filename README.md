一个简约的私有化MiniWiki部署


**🐳 一键部署**<br>
```
管理页面: http://你的服务器IP:9111/admin （编辑内容/管理账号/管理密码）
对外页面: http://你的服务器IP:9111
```
<br>

```
docker run -d \
  --name miniwiki \
  --restart=unless-stopped \
  --network host \
  -e TZ=Asia/Shanghai \
  -v <配置文件存放路径>:/Config \
  nextemby/miniwiki:latest
```
<br>

```
services:
  nextemby:
    image: nextemby/miniwiki:latest
    container_name: miniwiki
    restart: unless-stopped
    network_mode: host
    environment:
      - TZ=Asia/Shanghai
    volumes:
      - <配置文件存放路径>:/Config
```
<br>

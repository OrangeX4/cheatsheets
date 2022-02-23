---
title: linux
categories: server
---

## get started

### Process

```bash
# 后台执行
nohup <command> &

# 查找进程
ps aux | grep <command>
```

### File

```bash
# 给文件设置可执行权限
chmod 777 run.sh
```

### User

```bash
# 新建用户
useradd -m <user>

# 设置密码
passwd <user>

# 删除用户
userdel <user>

# 删除用户及用户文件夹
userdel -r <user>

# 赋予 root 权限
vim /etc/sudoers
# <user> ALL=(ALL) ALL
```

### Server

```bash
# 开启黑白棋
nohup python3 ./reversi/main.py &
nohup python3 ./reversi/network.py &
cd /home/ubuntu/reversi/templates
nohup sudo http-server --port=80 -s &

# 开启数据库
cd /usr/local/mongodb/bin
./mongod --bind_ip "0.0.0.0" --dbpath /var/lib/mongo --logpath /var/log/mongodb/mongod.log --fork --config /usr/local/mongodb/bin/mongod.cfg --auth
# 停止数据库
./mongod --dbpath /var/lib/mongo --logpath /var/log/mongodb/mongod.log --shutdown

# 星移服务器端
cd /home/ubuntu/reversi
git pull
mvn package
nohup java -jar target/todos-0.0.1-SNAPSHOT.jar > /dev/null &

# RssHub 服务
sudo docker rm rsshub
sudo docker run -d --rm --name rsshub -p 1200:1200 -e CACHE_EXPIRE=30 -e GITHUB_ACCESS_TOKEN=<token> diygod/rsshub
```
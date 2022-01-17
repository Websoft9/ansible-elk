# 服务启停

使用由Websoft9提供的 ELK 部署方案，可能需要用到的服务如下：

### ELK

```shell
sudo systemctl start elk-elasticsearch | elk-logstash | elk-kibana
sudo systemctl stop elk-elasticsearch | elk-logstash | elk-kibana
sudo systemctl restart elk-elasticsearch | elk-logstash | elk-kibana
sudo systemctl status elk-elasticsearch | elk-logstash | elk-kibana
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

### Docker-Compose
```
#创建容器编排
sudo docker-compose up -d

#删除容器编排
sudo docker-compose up -d

#启动/停止/重启
sudo docker-compose start
sudo docker-compose stop
sudo docker-compose restart
```

### Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```

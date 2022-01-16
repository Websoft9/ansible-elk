# ELK

ELK 即 Elastic Stack， 它是官方标准的名称。
值得注意的是，ELK 中所有组件的版本必须保持一致（精确到小版本）

> If you are using Elasticsearch 7.16.3, you install Beats 7.16.3, APM Server 7.16.3, Elasticsearch Hadoop 7.16.3, Kibana 7.16.3, and Logstash 7.16.3.

## 安装

1.使用docker安装的时候必须要注意的地方：
    使用./vars/main.yml文件对Elastic 进行初始化的时候，如果没有设置common_install_docker: True, docker_install: False这两个值的话那么就会报错显示“docker 没有安装”

## 账号密码

ALL default username is elastic, password is changeme.  

ES 和 Logstash 都会与这个账号密码有关


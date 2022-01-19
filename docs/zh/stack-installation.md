# 初始化安装

在云服务器上部署 ELK 安装环境之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 ELK，请先到 **域名控制台** 完成一个域名解析
4. 登录云服务器，运行下面的命令，拉取 ELK 相关 Docker 镜像并启动容器
   ```
   cd /data/wwwroot/elk && docker-compose pull && docker-compose up -d
   ```

   > Elastic 开源版 License 不允许第三方的分发行为，但允许用户免费使用，故需自行获取镜像。

## ELK 安装向导

1. 使用本地电脑浏览器访问网址：*http://域名* 或 *http://服务器公网IP*, 进入 ELK 登录界面
   ![ELK 登录页面](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-login-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#elk)），成功登录到 ELK 后台  
   ![ELK 后台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-bkreminder-websoft9.png)
   ![ELK 控制台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-dashboard-websoft9.png)

> 需要了解更多 ELK 的使用，请参考官方文档：[ELK Documentation](https://www.elk.com/documentation.html)

## ELK 入门向导

ELK的数据源多种多样，这里用常见的日志文件为Logstash的输入为例，步骤如下：

1. 在Logstash的配置文件logstash.conf设置索引"mytest"，并重启容器

```
input{
    file{
        path => "/var/log/yum.log"
        type => "elasticsearch"
        start_position => "beginning"
    }
}

output {
	elasticsearch {
		hosts => "elasticsearch:9200"
		user => "elastic"
		password => "elastic123"
                index => "mytest"
	}
}
```
2. 验证Elasticsearch和Logstash是否成功连接，索引数据是否生效(通过URL验证：http://服务器公网IP:9200/mytest/_cat/indices?v)

  ![ELK URL验证页面](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard1-websoft9.png)
  
3. 登陆Kibana，点击【Manage】，再点击右侧菜单的【Index Patterns】

  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard2-websoft9.png)
  
  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard3-websoft9.png)

4. 检索"mytest"，根据提示完成创建

  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard4-websoft9.png)
  
  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard5-websoft9.png)
  
5. 索引在Kibana创建成功，可以用时间条件在此检索数据

  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard6-websoft9.png)
  
  ![ELK Index](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-wizard7-websoft9.png)

## 常见问题

#### 浏览器打开IP地址，无法访问 ELK（白屏没有结果）？

您的服务器对应的安全组 80 端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 本部署方案采用什么安装方式

Docker

# FAQ

#### How can I enable the debug mode of ELK service?

```
systemctl stop elk-server
elk-server console
```

#### Can I reset password of ELK by command?

Yes, e.g `elkctl change_password  admin newpassword`

#### If there is no domain name, can I deploy ELK?

Yes, access ELK by *http://Server's Internet IP:8161*.

#### What is the password for the database root user?

The password is stored in the server related file `/credentials/password.txt`.

#### Is there a web-base GUI database management tool?

Yes, phpMyAdmin is included. Visit by *http://Server's Internet IP:9090*.

#### Is it possible to modify the source path of ELK?

No.

#### How to change the permissions of filesystem?

Change owner(group) or permissions as below:

```shell
chown -R apache.apache /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a series of software to the server in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference. All refer to cloud servers. They are the different terminology used by manufacturers.

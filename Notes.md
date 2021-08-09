1.使用docker安装的时候必须要注意的地方：
    使用./vars/main.yml文件对Elastic 进行初始化的时候，如果没有设置common_install_docker: True, docker_install: False这两个值的话那么就会报错显示“docker 没有安装”

2.使用docker安装elastic的时候，设置虚拟内存vm.max_map_count=262144是对宿主机中,而不是容器内部

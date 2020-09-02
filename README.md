# armv8_dockcross_help

```shell script
# 安装docker
sudo apt-get update
sudo apt -y install docker.io  

#修复权限问题
sudo groupadd docker     #添加docker用户组
sudo gpasswd -a $USER docker     #将登陆用户加入到docker用户组中
newgrp docker     #更新用户组
docker ps    #测试docker命令是否可以使用sudo正常使用

#添加阿里源
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://x9o4p9lt.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker

#安装 dockcross/linux-arm64
docker pull dockcross/linux-arm64

```

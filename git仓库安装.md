# gitea
git仓库安装

安装详情 如下 

https://docs.gitea.io/zh-cn/install-from-binary/


wget  https://dl.gitea.io/gitea/1.9/gitea-1.11.1-linux-amd64

cat  /usr/lib/systemd/system/gitea.service

[Unit]
Description=gitea

[Service]
User=root
ExecStart=/usr/local/gitea/gitea
Restart=on-abort

[Install]
WantedBy=multi-user.target

systemctl daemon-reload

systemctl gitea restart

gitea 支持lfs 

安装 Git LFS 需要 Git 的版本不低于 1.8.5

升级git 
#安装源
yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-2.noarch.rpm

#安装git

yum install git

#更新git

yum update git

客户端安装 git-lfs 
wegt https://packagecloud.io/github/git-lfs/packages/el/7/git-lfs-2.11.0-1.el7.x86_64.rpm

yum install git-lfs

git lfs install

执行 git lfs install 开启lfs功能
使用 git lfs track 命令进行大文件追踪 例如git lfs track "*.png" 追踪所有后缀为png的文件
使用 git lfs track 查看现有的文件追踪模式
提交代码需要将gitattributes文件提交至仓库. 它保存了文件的追踪记录
提交后运行git lfs ls-files 可以显示当前跟踪的文件列表
将代码 push 到远程仓库后，LFS 跟踪的文件会以『Git LFS』的形式显示:
clone 时 使用'git clone' 或 git lfs clone均可


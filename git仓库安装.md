# gitea
git仓库安装

安装详情 如下 

https://docs.gitea.io/zh-cn/install-from-binary/


wget  https://dl.gitea.io/gitea/1.9/gitea-1.9-linux-amd64


[Unit]
Description=gitea

[Service]
User=root
ExecStart=/usr/local/gitea/gitea
Restart=on-abort

[Install]
WantedBy=multi-user.target


systemctl gitea restart

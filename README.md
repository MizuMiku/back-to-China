# back-to-China
wulabing v2ray回国(内地)搭建 使用请遵守中国内地法律

用finalshell在境外VPS上用 https://github.com/cchhuuaann1/httpproxy 脚本安装http代理 跑一遍wulabing的脚本 然后进入 /data/ 目录 把那两个v2ray证书下载下来(右击 下载) 在桌面上会有一个文件夹"fsdownload"在那里面 然后SSH登录境内VPS(NAT和独立IP都可以)创建 /data/ 目录 把那两个v2ray证书上传到 /data/ 去 给内地VPS挂http代理( `export http_proxy=http://ip:port export https_proxy=http://ip:port`) 接着在境内VPS上再跑一边跑wulabing的脚本 域名那里直接填当前IP回车 输入yes继续安装 宽口那块NAT的VPS填一个你可以使用的端口 独立IP的除了80/443以外的其他任意一个端口 跑完脚本后取消掉http代理 `unset http_proxy unset https_proxy` 

因为中国大陆的一些原因 VPS需要换源 我这里给换阿里云源的方法
centos7换源

`mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup`

`wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo`

`yum clean all`

`yum makecache`

centos8换源

`mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup`

`wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo`

`dnf clean all`

`dnf makecache`

debian9换源

`mv /etc/apt/sources.list /etc/apt/sources.list.backup`

`echo "
deb http://mirrors.aliyun.com/debian/ stretch main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch main non-free contrib
deb http://mirrors.aliyun.com/debian-security stretch/updates main
deb-src http://mirrors.aliyun.com/debian-security stretch/updates main
deb http://mirrors.aliyun.com/debian/ stretch-updates main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch-updates main non-free contrib
deb http://mirrors.aliyun.com/debian/ stretch-backports main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch-backports main non-free contrib
" > /etc/apt/sources.list `

`chmod 644 /etc/apt/sources.list`

debian10换源

`mv /etc/apt/sources.list /etc/apt/sources.list.backup`

`echo "
deb http://mirrors.aliyun.com/debian/ buster main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib
deb http://mirrors.aliyun.com/debian-security buster/updates main
deb-src http://mirrors.aliyun.com/debian-security buster/updates main
deb http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib
deb http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib
" > /etc/apt/sources.list `

`chmod 644 /etc/apt/sources.list`

ubuntu18.04换源

`mv /etc/apt/sources.list /etc/apt/sources.list.backup`

`echo "
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
" > /etc/apt/sources.list `

`chmod 644 /etc/apt/sources.list	`	
 
 ubuntu20.04换源
 
`mv /etc/apt/sources.list /etc/apt/sources.list.backup`

`echo "
deb http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse
" > /etc/apt/sources.list `

`chmod 644 /etc/apt/sources.list	`

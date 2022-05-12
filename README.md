# 钉钉内网穿透客户端（基于ngrok1.7）

### 为了想在自己的小米路由器3 MT7620A处理器 mipsle上的跑钉钉的内网穿透，于是自己参考了[树莓派的钉钉内网穿透客户端编译](https://blogs.minifake.xyz/2021/09/%E7%BC%96%E8%AF%91ngrok%E5%AE%A2%E6%88%B7%E7%AB%AF%EF%BC%88%E8%BF%9E%E6%8E%A5%E9%92%89%E9%92%89%E7%A9%BF%E9%80%8F%E7%9A%84%E5%9F%9F%E5%90%8D%EF%BC%89)

## 编译环境
- Ubuntu 20.04 amd64
- go 1.18

go 1.18 已经支持mips mipsel这些交叉编译环境了，可以给自己芯片的路由器上编译自己的客户端，十分的方便。

## 安装依赖
```shell
apt-get install git make
```

## 编译
```shell
git clone https://github.com/wes-lin/pierced-ngrok.git
go env -w GO111MODULE=auto
cd pierced-ngrok
./make-ngrok.sh vaiwan.com
```
很多依赖都是github上的，所以下载时候很容易错误，如果编译失败了，建议多试几次，我的渣渣网络就经常出问题，有条件的同学可以挂一下梯子，因为[ngrok1.7](https://github.com/inconshreveable/ngrok)的源码很久远了，其中很多依赖找不到了，我修改了源码里一些依赖地址。

## 使用
编译成功后，可以在release文件下看到许多版本的ngrok客户端，找到自己需要的版本，拷贝出来重名成ding。 

![](https://cdn.jsdelivr.net/gh/wes-lin/pierced-ngrok/assets/info.png)
![](https://cdn.jsdelivr.net/gh/wes-lin/pierced-ngrok/assets/run.png) 

具体使用可以看[钉钉的官方文档](https://open.dingtalk.com/document/resourcedownload/http-intranet-penetration)，不想编译的同学可以直接下载我这边二进制版本，或者等待我的pr到钉钉的[官方仓库](https://github.com/open-dingtalk/pierced)。

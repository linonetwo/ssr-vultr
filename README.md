# ssr-vultr
在vultr上，在线自动部署ssr

自动部署v2ray，[v2ray-vultr](https://github.com/lbp0200/v2ray-vultr)

>只支持Ubuntu 18.04

目前Vultr在搞活动，新注册用户，充50送25，可以考虑新建的小号薅羊毛，需要老用户邀请，附上邀请链接[https://www.vultr.com/?ref=7576590](https://www.vultr.com/?ref=7576590)

下方视频教程：
---
[![在线自动部署shadowsocksR](https://img.youtube.com/vi/4Rgd09WFkas/0.jpg)](https://www.youtube.com/watch?v=4Rgd09WFkas)


使用方法
---

### 第一步

打开[Vultr](https://polr.liuboping.com/PrgTf)，登录之后，在`Servers`-`Startup Scripts`-`Add Startup Script`

`name` 随便填

`Type`->`Boot`

最后一项，打开[VultrStartupScript.sh](https://raw.githubusercontent.com/linonetwo/ssr-vultr/master/VultrStartupScript.sh)，复制里面的内容，粘贴进去

第二行是参数

PASSWORD 填你自己的密码

PORT 为端口号

最后，点最下方蓝色按钮`Add Script`

### 第二步 部署服务器

新建服务器

`Server Type`选择 Ubuntu 18.04

5.`Startup Script`，选中刚才新建的`Startup Script`

> 完成服务器的部署，等待服务器部署完成

ssr客户端的配置文件在 https://github.com/linonetwo/ssr-vultr/blob/master/config.json 模板如下：

```json
{
    "server": "VPS_IP",
    "server_port": 443,
    "local_address": "0.0.0.0",
    "local_port": 1083,
    "password": "password",
    "method": "aes-128-ctr",
    "protocol": "auth_aes128_md5",
    "protocol_param": "",
    "obfs": "tls1.2_ticket_auth",
    "obfs_param": "",
    "speed_limit_per_con": 0,
    "speed_limit_per_user": 0,
    "additional_ports": {},
    "additional_ports_only": false,
    "timeout": 120,
    "udp_timeout": 60,
    "dns_ipv6": false,
    "connect_verbose_info": 0,
    "redirect": "",
    "fast_open": false
}
```

其中的 password 会被自动替换成 StartupScript 中定义的 PASSWORD

功能
---
已启用bbr加速

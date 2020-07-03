# aliddns-ipv6

## 简介

本脚本为shell版阿里云dddns IPV6解析,理论支持IPV4（前提是要修改对应的地方，脚本内有说明)
目前测试可用，反正只有几十行，不行自己改改呗O(∩_∩)O😄

## 功能

* shell内分几块：设定区、IP获取区、域名的解析区
* 脚本比较小，不借助SDK，部署方便快捷
* 反正我也不会再增加功能了😄

## 用法

### 1、改密码O(∩_∩)O，就是修改账号密码的意思。。。
修改脚本：
```bash
#下面引号内改成你的阿里ak
      aliddnsipv6_ak="修改我"
#下面引号内改成你的阿里sk，说白了这俩就是账号和密码
      aliddnsipv6_sk="修改我"
```

### 2、改需要解析的域名
`aliddnsipv6_name1`是域名前缀，就是xxx.baidu.com里面的xxx，`aliddnsipv6_domain`是主域名，就是xxx.com：
```bash
#下面引号内改成你要解析域名的前缀，如果是根域名直接填写@
      aliddnsipv6_name1="修改我"
#下面引号内改成你要解析的主域名，例如：baidu.com  
      aliddnsipv6_domain="修改我"
#下面引号内改成你需要的解析切换时间，这个阿里默认最快600秒，花钱才能改小
      aliddnsipv6_ttl="600"
```
  
### 3、 运行脚本
推荐用bash：
```bash
	bash aliddns-ipv6
```
bash 运行脚本后，观察情况，一般3秒结束。。。
### 4、定时启动
当然用`crontab`
```bash
crontab -e
# 在编辑器里面搞些东西
*/10 * * * * bash /root/aliddns-ipv6
#后面的路径自己选择哈，你放哪都行

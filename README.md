# 最近ChatGPT 和 Midjourney 很火啊，给大家推荐一个可以免费体验这俩的网址，http://easyai.fit gpt3.5 免费的 不需要注册,支持上下文对话,还支持 Midjourney

# NPS

[README](https://github.com/ehang-io/nps/blob/master/README.md)|[中文文档](https://github.com/ehang-io/nps/blob/master/README_zh.md)

# 说明
由于nps已经有一年多的时间没有更新了，存留了不少bug和未完善的功能。

此版本基于 nps 0.26.10的基础上二次开发而来。

***DockerHub***： [NPS](https://hub.docker.com/r/yisier1/nps) [NPC](https://hub.docker.com/r/yisier1/npc)



## 更新日志

- 2023-02-24  v0.26.15  
  ***修复***：更新程序 url 更改到当前仓库中   
  ***修复***：nps 在外部路径启动时找不到配置文件  
  ***新增***：增加 nps 启动参数，`-conf_path=D:\test\nps`,可用于加载指定nps配置文件和web文件目录。  
  ***window 使用示例：***  
  直接启动：`nps.exe -conf_path=D:\test\nps`  
  安装：`nps.exe install -conf_path=D:\test\nps`    
  安装启动：`nps.exe start`      

  ***linux 使用示例：***    
  直接启动：`./nps -conf_path=/app/nps`  
  安装：`./nps install -conf_path=/app/nps`  
  安装启动：`nps start -conf_path=/app/nps`  



- 2022-12-30  v0.26.14  
  ***修复***：API 鉴权漏洞修复


- 2022-12-19  
***修复***：某些场景下丢包导致服务端意外退出  
***优化***：新增隧道时，不指定服务端口时，将自动生成端口号  
***优化***：API返回ID, `/client/add/, /index/addhost/，/index/add/ `   
***优化***：域名解析、隧道页面，增加[唯一验证密钥]，方便搜查  


- 2022-10-30   
***新增***：在管理面板中新增客户端时，可以配置多个黑名单IP，用于防止被肉鸡扫描端口或被恶意攻击。  
***优化***：0.26.12 版本还原了注册系统功能，使用方式和以前一样。无论是否注册了系统服务，直接执行 nps 时只会读取当前目录下的配置文件。


- 2022-10-27  
***新增***：在管理面板登录时开启验证码校验，开启方式：nps.conf `open_captcha=true`，感谢 [@dongFangTuring](https://github.com/dongFangTuring) 提供的PR  

  
- 2022-10-24:     
***修复***：HTTP协议支持WebSocket(稳定性待测试)
  

- 2022-10-21:   
***修复***：HTTP协议下实时统计流量，能够精准的限制住流量（上下行对等）  
***优化***：删除HTTP隧道时，客户端已用流量不再清空


- 2022-10-19:  
***BUG***：在TCP协议下，流量统计有问题，只有当连接断开时才会统计流量。例如，限制客户端流量20m,当传输100m的文件时，也能传输成功。  
***修复***：TCP协议下实时统计流量，能够精准的限制住流量（上下行对等）  
***优化***：删除TCP隧道时，客户端已用流量不再清空
![image](image/new/tcp_limit.png)


- 2022-09-14:  
修改NPS工作目录为当前可执行文件目录（即配置文件和nps可执行文件放在同一目录下，直接执行nps文件即可），去除注册系统服务，启动、停止、升级等命令


# 搭建SSR服务

## 第一步: 购买服务器
[vultr](https://www.vultr.com)

- 购买服务器

- 可选微信或者支付宝付款

- 选择系统，套餐:Ubuntu19;5美元一个月

- 记录服务器信息:

  ```
  IP:xxx.xxx.xxx.xxx
  UserName:root
  PassWord:******
  ```

  
## 第二步: 配置在远程服务器上配置SSR服务
- ssh远程连接工具[putty](https://the.earth.li/~sgtatham/putty/latest/w64/putty-64bit-0.71-installer.msi)

- 登录到购买好的远程服务器
  
  - 如遇登录超时，登录不上可能的原因是IP地址被封掉了，需要删除远程服务器，然后重复第一步。
  
- 配置SSR:

  仿照下面来配置SSR服务器:

  ```
  Your Server IP        :  xxx.xxx.xxx.xxx 
  Your Server Port      :  8388 
  Your Password         :  jack
  Your Protocol         :  auth_aes128_md5 
  Your obfs             :  http_simple 
  Your Encryption Method:  chacha20 
  ```

  

  ```bash
  wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
  ```

  ```bash
  chmod +x shadowsocks-all.sh
  ```

  ```bash
  ./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
  ```

  

- 记录配置信息。

PS：一些以后可能会用到的命令:

```bash
#启动SSR：
/etc/init.d/shadowsocks-r start

#退出SSR：
/etc/init.d/shadowsocks-r stop

#重启SSR：
/etc/init.d/shadowsocks-r restart

#SSR状态：
/etc/init.d/shadowsocks-r status

#卸载SSR：
./shadowsocks-all.sh uninstall
```



## 第三步：使用SSR客户端
- SSR客户端
  - Windows: [下载连接](https://github.com/shadowsocksrr/shadowsocksr-csharp/releases/download/4.9.0/ShadowsocksR-win-4.9.0.zip)
  - Android: [这里下载](https://github.com/shadowsocksrr/shadowsocksr-android/releases)



三个步骤，应该就可以了。Bye。

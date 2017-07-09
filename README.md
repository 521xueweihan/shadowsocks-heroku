> Fork 于 [shadowsocks-heroku](https://github.com/mrluanma/shadowsocks-heroku) 项目

# shadowsocks-heroku
[Heroku](https://www.heroku.com/) 是一个支持多种编程语言的云平台即服务，shadowsocks-heroku 则是可部署在 Heroku 平台的 ss 服务。
和 [shadowsocks](https://github.com/clowwindy/shadowsocks) 不同的是 shadowsocks-heroku 使用的 WebSocket 代替原本的 sockets。

跟着下面的步骤，预计 **十分钟后**，你就可以 Google 了👻。

## 如果遇到问题
1. 请先检查是否遵循步骤（再次阅读一遍教程）
2. 请先自行通过搜索引擎寻找答案
3. 如果还没有解决，欢迎创建[ issue](https://github.com/521xueweihan/shadowsocks-heroku/issues/new) 提问

## 一、准备

### 1. 注册 Heroku 帐号
Heroku 提供免费账号，部分介绍如下：
- 512 MB RAM per dyno
- Free apps sleep automatically after 30 mins of inactivity to conserve your dyno hours
- Free apps wake automatically when a web request is received

用作 VPS 是够了，注册地址：https://signup.heroku.com/

### 2. Fork 本项目
1. Fork 本项目到个人账号下
    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/4-min.png)

2. 下载本项目到本地：“Clone or download” ——> “Download ZIP”
    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/8-min.png)

3. 解压文件，**并记下所在位置**

## 二、部署
Heroku 在创建项目的时候可以通过关联 GitHub 账号，直接部署 GitHub 账号下的项目。具体步骤如下：

1. 登陆 Heroku 帐号，后进入 Dashboard ——> Create New App ——> 输入 App Name

2. 完成上一步后，会跳转到 Deploy 页面，找到 Deployment method 选择 GitHub 关联上自己的 GitHub 帐号。

3. 关联上 shadowsocks-heroku 项目，如下图所示：
    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/1-min.png)

4. 点击 Deploy Branch，部署成功如下图：
    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/2-min.png)

## 三、设置加密算法和密码
进入 Setting 页面 ——> Reveal Config Vars，设置参数如下图：
![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/3-min.png)

**支持的加密算法类型如下：**  
- rc4-md5
- aes-256-cfb
- camellia-256-cfb

## 四、启动本地 Client
1. [安装 npm 教程](http://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/00143450141843488beddae2a1044cab5acb5125baf0882000)

2. **用命令行（终端或 cmd）**，进到上述**解压出来的文件夹（目录）**

3. 执行 `npm install -g` 命令，安装依赖的库（如 [npm 安装依赖慢请参考本篇文章](http://www.cnblogs.com/xueweihan/p/5491730.html)）

4. **确保当前目录** 下有 `local.js` 文件，然后启动本地 client 命令格式：`node local.js -s 你的app名称.herokuapp.com -l 1080 -m 设置的加密算法 -k 设置的密码 -r 80`

5. 启动成功，命令行显示：`server listening at { address: '127.0.0.1', family: 'IPv4', port: 1080 }`

## 五、最后
1. 下载：Chrome 浏览器 [SwitchyOmega](https://github.com/FelisCatus/SwitchyOmega/releases/download/v2.3.21/SwitchyOmega.crx) 插件，如果下载地址失效，可以在本项目下的 download 下找到 `SwitchyOmega.crx` 文件

2. 安装：打开浏览器的扩展程序页面 `chrome://extensions`，把 `SwitchyOmega.crx` 文件拖放到浏览器扩展程序页面安装

3. 配置：SwitchyOmega，如下图：
    ```
    代理协议：SOCKS5
    代理服务器：127.0.0.1
    代理端口：1080
    ```

    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/5-min.png)

4. 选择代理（刚配置好的）

    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/6-min.png)

5. 现在你就可以访问 Google 了

    ![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/7-min.png)

## 六、送人玫瑰手留余香🌹

![](https://github.com/521xueweihan/shadowsocks-heroku/blob/master/img/weixin.png)

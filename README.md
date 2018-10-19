# 1、「1024机器人大作战」滴滴云服务器领取&使用文档

欢迎参加 **「1024 机器人大作战」** 线上 `Hackathon`，本次活动由 **滴滴云** 提供云服务器支持。
**以下是本次活动滴滴云服务器使用攻略：**
### 一、 如何获得代金券
1、注册[倍洽](https://dc.tt/signup)&[滴滴云](https://app.didiyun.com/#/auth/signup?channel=14190)账号，用于账号升级与服务器的发放；

2、提交[大赛报名](https://dc.tt/2Rtuv)信息；

3、报名信息验证通过后，代金券将发放到注册账户；


注：
- 服务器配置：1核CPU 2GB内存 40G根盘 2M带宽
- 代金券领取时间：2018年10月19日-2018年11月5日 0：00
- 滴滴云为本次活动支持的服务器仅供参赛者用于本次比赛，若有违规将取消服务器使用权限

### 二、 如何使用代金券
**Step 1：登录滴滴云账号，点击“控制台”**

![pic1](http://bearychat.oss-cn-beijing.aliyuncs.com/stage1.png)

**Step 2：点击查看“代金券”**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage2.png)

**Step 3：确认“1024 程序员节活动券”发放至账户，并关注使用条件**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage3.png)

**Step 4：点击“账户设置”**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage4.png)

**Step 5：完成实名认证并绑定邮箱**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage5.png)

**Step 6：回到滴滴云官网首页，选择“产品-云服务器（DC2)”**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage6.png)

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage62.png)

**Step 7：点击“立即体验”**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage7.png)

**Step 8：按下图配置要求创建云服务器**

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage8.png)

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage82.png)

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage83.png)

![pic](http://bearychat.oss-cn-beijing.aliyuncs.com/stage84.png)




## 如何进行机器人开发环境的搭建
### 使用 `JavaScript` 进行开发
#### `Node` 环境搭建
```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
验证是否安装成功
```bash
node -v     ## v10.12.0
```
其他平台的安装可以参考 [通过包管理工具安装 Node](https://nodejs.org/en/download/package-manager/)

#### `SDK` 安装和使用
可以直接参照这里完成我们的安装 [BearyChat JS SDK](https://github.com/bearyinnovative/bearychat.js/blob/master/README.md)
或者我们可以直接下面的命令进行安装
```bash
npm install bearychat -g
```
测试：
```javascript
const bearychat = require('bearychat');
bearychat.user.list({
  token: "<your token>"
}).then(resp => resp.json())
  .then(data => console.log(data));

/*
users response
[
  {
    "inactive": false,
    "role": "normal",
    "email": "support@bearyinnovative.com",
    "name": "BearyBot",
    "type": "assistant",
    "created": "2017-01-11T12:28:31.000+0000",
    "id": "=bwMkR",
    "avatars": {
      "small": null,
      "medium": null,
      "large": null
    },
    "team_id": "=bw52O",
    "full_name": "倍洽小助手",
    "mobile": null,
    "profile": {
      "bio": null,
      "position": null,
      "skype": null
    }
  }
]
*/
```

更多用法请查看：[Full API Documentation of BearyChat JavaScript SDK](https://github.com/bearyinnovative/bearychat.js/blob/master/API.md)

### 使用 `Python` 进行开发
#### 搭建 `Python` 开发环境
由于滴滴云的 `ubuntu 16.04` 镜像已经预装了 `Python 2.7.12` 了，所以我们可以跳过安装 `python` 这一步。
验证是否安装完成
```bash
python --version
```

#### `SDK` 安装和使用
可以直接参照这里完成我们的安装 [BearyChat Python SDK](https://github.com/bearyinnovative/bearychat.py/blob/master/README.md)
或者我们可以直接下面的命令进行安装
```bash
pip install bearychat
```
测试：
```python
from bearychat import openapi
client = openapi.Client('<Your Hubot Token>')
client.channel.list()
'''
[{u'latest_ts': 1539328483074, u'member_uids': [u'=bwZbY', u'=bwZQY', u'=bxat5'], u'name': u'\u6240\u6709\u4eba', u'is_member': False, u'is_active': True, u'private': False, u'general': True, u'topic': None, u'team_id': u'=bwDBo', u'vchannel_id': u'=bwPzN', u'type': u'normal', u'id': u'=bwPzN', u'uid': u'=bwZbY'}]
'''
```

###  使用 `Go` 进行开发
####  `Go` 环境搭建
安装 `Go` 可以参照官网的[文档](https://golang.org/doc/install)
我们在滴滴云上是这样做的
```bash
wget https://dl.google.com/go/go1.11.1.linux-amd64.tar.gz
sudo tar -C /usr/local/ -xzf go1.11.1.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
```

#### `SDK` 的安装和使用
安装可以参照我们的 [`Bearychat Go SDK`](https://github.com/bearyinnovative/bearychat-go)
我们在滴滴云上是这样做的
```bash
go get -u -v github.com/bearyinnovative/bearychat-go
```
测试：
```
package main

import (
       "context"
       "fmt"
       "encoding/json"

       "github.com/bearyinnovative/bearychat-go/openapi"
)

func main() {
       client := openapi.NewClient('<your-hubot-token>')
       me, resp, err := client.User.Me(context.Background())
       meJson, _ := json.Marshal(me)
       fmt.Println(resp.Status)
       fmt.Println(string(meJson))
       fmt.Println(err)
}


200 OK
{"id":"=bxcdF","team_id":"=bw52O","email":"hubot-a8ce42139a832e77c5f7ef564c044a31@bearychat.com","name":"假的sara","type":"hubot","role":"normal","avatars":{},"profile":{},"inactive":false,"created":"0001-01-01T00:00:00+0000"}
<nil>
```

## 如何在 滴滴云 部署机器人（注：此文档基于 Ubuntu 16.04）
### 上传项目到服务器
#### 在 `Linux` 上传文件
##### 使用 `scp` 进行上传
```bash
scp -r /path/to/your/project dc2-user@<your didi server ip address>:~
```

##### 使用 `Git` 进行上传
1. 下载 [Git](http://git.oschina.net/progit/1-%E8%B5%B7%E6%AD%A5.html#1.4-%E5%AE%89%E8%A3%85-Git)
2. 上传项目代码，关于如何上传项目可以参考 [取得项目的 git 仓库](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.1-%E5%8F%96%E5%BE%97%E9%A1%B9%E7%9B%AE%E7%9A%84-Git-%E4%BB%93%E5%BA%93) 和 [远程仓库的使用](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.5-%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8)
3. 在滴滴云上使用 `Git` 拉取项目 （滴滴云已预装 `Git`），可以参考  [取得项目的 git 仓库](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.1-%E5%8F%96%E5%BE%97%E9%A1%B9%E7%9B%AE%E7%9A%84-Git-%E4%BB%93%E5%BA%93) 和 [远程仓库的使用](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.5-%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8)
4. 部署项目


####  在 `Windows` 上传文件
##### 使用  `Winscp` 进行上传
参考文档 [好用的服务器文件上传方式 WinScp](https://blog.csdn.net/weixin_41855467/article/details/80847059)

##### 使用  `Git` 进行上传
1. 下载  [`Git For Windows`](https://gitforwindows.org/)
2. 上传项目代码，关于如何上传项目可以参考 [取得项目的 git 仓库](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.1-%E5%8F%96%E5%BE%97%E9%A1%B9%E7%9B%AE%E7%9A%84-Git-%E4%BB%93%E5%BA%93) 和 [远程仓库的使用](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.5-%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8)
3. 在滴滴云上使用 `Git` 拉取项目 （滴滴云已预装 `Git`），可以参考  [取得项目的 git 仓库](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.1-%E5%8F%96%E5%BE%97%E9%A1%B9%E7%9B%AE%E7%9A%84-Git-%E4%BB%93%E5%BA%93) 和 [远程仓库的使用](http://git.oschina.net/progit/2-Git-%E5%9F%BA%E7%A1%80.html#2.5-%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8)
4. 部署项目

# 2、「1024机器人大作战」机器人 demo 文档

## 机器人 Demo
##### 如何搭建一个已经开发完成的机器人
---

### [北京浮生记](https://mp.weixin.qq.com/s/1M3lj0Wjk2PNXUJRocWseg)

#### 获取项目
``` bash
git clone https://github.com/shadeofgod/beijing-hell
```

#### 创建 `Hubot`
1. 登陆你的团队，[点此登陆](https://bearychat.com/start)
2. 添加创建 `Hubot`，[如何添加机器人](https://bearychat.help/normal/robot.html#%E6%B7%BB%E5%8A%A0%E6%9C%BA%E5%99%A8%E4%BA%BA)
3. 保存我们的 `Hubot Token` 用作后续使用

#### 配置我们的项目
```bash
cd /path/to/beijing-hell
echo "export const HUBOT_TOKEN = '<YOUR OWN HUBOT TOKEN>';" > ./packages/bearyhubot/src/token.js     ## YOUR OWN HUBOT TOKEN 填写你上一步获得的 token
```

#### 运行 `Hubot`
```bash
npm install
npm run prepare
npm run dev:hubot
```
这样就完成了我们 `Hubot` 的启动

![Alt text](http://bearychat.oss-cn-beijing.aliyuncs.com/70f9e5b5-e7a0-4508-82b9-b8e2703a74b2.png)


### [Bug 修复机器人](https://mp.weixin.qq.com/s/1M3lj0Wjk2PNXUJRocWseghttps://mp.weixin.qq.com/s/CIv32GZOcn3qXmz4PxAONA)

#### 获取项目
``` bash
git clone https://github.com/a972667237/bug
```

#### 创建 `Incoming` 机器人
1. 登陆你的团队，[点此登陆](https://bearychat.com/start)
2. 添加创建 `Incoming` 机器人，[如何添加机器人](https://bearychat.help/normal/robot.html#%E6%B7%BB%E5%8A%A0%E6%9C%BA%E5%99%A8%E4%BA%BA)
3. 保存我们的 `Webhook Url` 用作后续使用

#### 准备环境
```bash
python3 -m virtualenv venv

echo  "export PIP_CONFIG_FILE=\"$(pwd)/../pip.conf\"" >> venv/bin/activate

echo "[global]
index-url = http://pypi.douban.com/simple
[install]
trusted-host = pypi.douban.com" > venv/pip.conf

source venv/bin/activate

pip install -r requirements.txt
```

#### 运行 `Incoming` 机器人
```bash
python send_to_bc.py -g <repo-path> -u <repo-url> -w <webhook-url>
```
这样就完成了我们 `Bug` 机器人的启动

![Alt text](http://bearychat.oss-cn-beijing.aliyuncs.com/e327c77f-c52e-4062-96ad-a3c5fd58dfe7.png)


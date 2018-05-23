# CoolChat  

## 【此项目已经搁置，后台也不再提供登录以及Socket连接服务，可能会引起应用的崩溃】。

这是一款高仿“一块”App（英文名：yeeCall）的即时通讯的开源客户端，目前已经搁置！
服务端采用的是[GatewayWorker][16]框架，服务端代码仓库： https://github.com/CooLoongWu/CoolChatServer  。

## 测试账户  

由于涉及到即时通讯，所以客户端需要跟服务器端建立Socket连接，服务端用的是我自己搭建的阿里云服务器，如需测试请在工作日时间
09:00-18:00的时间段内进行测试，其他时间服务器暂时不提供Socket连接服务（也就是无法聊天），登录等服务正常提供。
请测试新版的的用户先把之前安装的旧版卸载，再安装新版本。因为数据库表等其他各种功能都做了较大改动，现在还没正式完成App所以没有做兼容，出现闪退请卸载重新安装即可。

### 用户列表  

|用户ID|账号|用户名|密码|
|------|:----:|:----:|:----:|
|1  |1  |黑崎一护        |12345  |
|2  |2  |朽木露琪亚      |12345  |
|3  |3  |市丸银         |12345  |
|4  |4  |朽木白哉        |12345  |
|5  |5  |日番谷冬狮郎     |12345  |
|6  |6  |松本乱菊        |12345  |
|7  |7  |乌尔奇奥拉·西法  |12345  |

### 好友关系  

  <table>
        <tr>
            <th>用户</th>
            <th>黑崎一护</th>
            <th>朽木露琪亚</th>
            <th>市丸银</th>
            <th>朽木白哉</th>
            <th>日番谷冬狮郎</th>
            <th>松本乱菊</th>
            <th>乌尔奇奥拉·西法</th>
        </tr>
        <tr>
            <td>黑崎一护</td>
            <td></td>
            <td>√</td>
            <td>√</td>
            <td>√</td>
            <td>√</td>
            <td>√</td>
            <td></td>
        </tr>
        <tr>
            <td>朽木露琪亚</td>
            <td>√</td>
            <td></td>
            <td></td>
            <td>√</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>市丸银</td>
            <td>√</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>√</td>
            <td></td>
        </tr>
        <tr>
            <td>朽木白哉</td>
            <td>√</td>
            <td>√</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>日番谷冬狮郎</td>
            <td>√</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>√</td>
            <td></td>
        </tr>
        <tr>
            <td>松本乱菊</td>
            <td>√</td>
            <td></td>
            <td>√</td>
            <td></td>
            <td>√</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>乌尔奇奥拉·西法</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </table>

### 群组用户关系列表  

|群组ID|用户ID|
|-----|:----:|
|1  |1  |
|1  |2  |
|1  |3  |
|1  |4  |
|1  |5  |
|1  |6  |

## 功能一览（未勾选的为待开发）  

Android端项目做到后面越来越觉得没有一个服务端的话简直无法正常进行下去，所以现在服务端使用了Laravel框架来进行
简单的Api的开发。（说明：其实我对PHP框架并没有多少了解，一开始打算使用ThinkPHP5的框架来写，毕竟国人开发，文档看起来相对也轻松点，
但是部署后由于路由那一块搞得比较头大，于是就放弃TP5转而选择了目前国外比较流行的Laravel框架。就目前而言，路由、控制器、
数据库用起来都非常顺手，所以目前就暂定使用该框架了。）

短视频的拍摄使用了“趣拍云”的SDK，由于需要绑定签名，所以大家在测试的时候可能会出现不能拍摄并崩溃的问题。后期我会将软件签名文件和
密码一并放出来供大家打包测试。

###  Android端  

- [x] **页面开发**
    - [x] 侧栏页面
    - [x] 聊天会话列表页面
    - [x] 联系人列表页面
    - [x] 与好友对话页面
    - [x] 联系人及群组详情页面
- [x] **功能开发**
    -  [x] 进行Socket通信
    -  [x] 给好友发送消息（包括文字、图片、音频、视频）
    -  [x] 给群组发送消息（包括文字、图片、音频、视频）
    -  [x] 聊天列表功能完成（实时刷新用户聊天内容）
    -  [x] 本地存储消息内容
    -  [x] 未读消息提醒
    -  [x] 消息撤回
    -  [x] 发送程序自带表情
    -  [ ] 添加、创建群组
    -  [ ] 添加好友

### 服务端  

- [x] 用户、好友列表、群组等数据库
- [x] 用户登录接口，暂不提供注册
- [x] 获取好友列表接口
- [x] 获取好友信息接口
- [x] 获取群组列表接口
- [ ] 添加好友接口
- [ ] 添加群组接口

## 已完成页面一览  

因为目前只有我一人在做，PS和AI能力也不强，所以图标素材什么的各位估计也清楚怎么来的。  
如有侵权请告知，我会尽快删除并更换！  

![image](./pictures/main_drawer.jpg) ![image](./pictures/main_empty_conversation.jpg) ![image](./pictures/main_empty_contact.jpg)
![image](./pictures/main_conversation.jpg) ![image](./pictures/main_contact.jpg) ![image](./pictures/chat_send.jpg)
![image](./pictures/chat_emoji.jpg) ![image](./pictures/chat_audio_image.jpg) ![image](./pictures/chat_audio.jpg)
![image](./pictures/chat_video.jpg) ![image](./pictures/chat_cancel.jpg) ![image](./pictures/chat_video_edit.jpg) 
![image](./pictures/chat_video_image_audio.jpg) ![image](./pictures/profile_me.jpg) ![image](./pictures/profile_other.jpg)

## 引用其他控件一览  

该app在开发中也引用了大量的第三方优秀控件、框架和SDK，感谢这些开源的作者
- [Clans/FloatingActionButton][3]
- [square/picasso][4]
- [greenrobot/EventBus][5]
- [greenrobot/greenDAO ][6]
- [hdodenhof/CircleImageView][8]
- [loopj/android-async-http][9]
- [lovetuzitong/MultiImageSelector][10]
- [Bilibili/ijkplayer][11]
- [crossbario/autobahn-android][12]
- [pengwei1024/LogUtils][13]
- [Tapadoo/Alerter][17]
- [afollestad/material-dialogs][18]
- [七牛云][14]
- [趣拍云][15]


## 已知Bug一览（带删除线的为已修复）  

- ~~自己发消息超过两行，文字会超出屏幕~~
- ~~聊天列表页清空后没有展示空页面~~
- ~~发送消息后点击“+”按钮则无法再发送消息~~
- ~~有时会导致一条消息发送多次~~
- ~~切换网络或者掉线时无法自动重连~~
- ~~从无网络进入聊天页面时发送消息闪退~~
- ~~魅蓝3手机中录音失败，无法发送录音~~
- ~~弹出键盘时候聊天区域无法自动向上滚动~~
- ~~录音结束后部分手机会崩溃~~
- 多图选择在魅蓝3手机中无法显示DCIM下的图片

##  License  

```
Copyright 2015 CooLoongWu

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

[CooLoongWu][2]
2016 年 09月 12日 

[1]:https://cooloongwu.github.io/
[2]:http://blog.csdn.net/u010976213
[3]:https://github.com/Clans/FloatingActionButton
[4]:https://github.com/square/picasso
[5]:https://github.com/greenrobot/EventBus
[6]:https://github.com/greenrobot/greenDAO
[7]:https://github.com/rockerhieu/emojicon
[8]:https://github.com/hdodenhof/CircleImageView
[9]:https://github.com/loopj/android-async-http
[10]:https://github.com/lovetuzitong/MultiImageSelector
[11]:https://github.com/Bilibili/ijkplayer
[12]:https://github.com/crossbario/autobahn-android
[13]:https://github.com/pengwei1024/LogUtils
[14]:http://www.qiniu.com/
[15]:https://www.qupaicloud.com/
[16]:hhttp://www.workerman.net/gatewaydoc/
[17]:https://github.com/Tapadoo/Alerter
[18]:https://github.com/afollestad/material-dialogs

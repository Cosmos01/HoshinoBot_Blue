# HoshinoBot Blue

[![License](https://img.shields.io/github/license/Ice9Coffee/HoshinoBot)](LICENSE)
![Python Version](https://img.shields.io/badge/python-3.8+-blue)
![Nonebot Version](https://img.shields.io/badge/nonebot-1.6.0%2B%2C%202.0.0---blue)


专为碧蓝档案整理的纯净版HoshinoBot  

A QQ-bot for Blue Archive based on [Nonebot](https://github.com/nonebot/nonebot)

不要clone本项目，移步[Release](https://github.com/Cosmos01/HoshinoBot_Blue/releases/tag/release)下载整合包

## 简介

**HoshinoBot:** 基于 [nonebot](https://docs.nonebot.dev/) 的开源Q群bot框架。


## 功能介绍

HoshinoBot_Blue 的功能开发以服务 [碧蓝档案](http://bluearchive.jp) 玩家为核心。

<details>
  <summary>主要功能</summary>

- **碧蓝档案**：[使用说明](https://github.com/Cosmos01/Blue_Archive_HoshinoBot#%E6%8C%87%E4%BB%A4%E5%88%97%E8%A1%A8)
- **B博转发**：[使用说明](https://github.com/kushidou/bili-notice-hoshino#%E4%BD%BF%E7%94%A8)

> 由于bot的功能会快速迭代开发，使用方式这里不进行具体的说明，请向bot发送"help"或移步[此文件](hoshino/modules/botmanage/help.py)查看详细。

</details>

<details>
  <summary>通用功能</summary>

- **掷骰子**：`.rd`
</details>

-------------

### 功能模块控制

HoshinoBot 的功能繁多，各群可根据自己的需要进行开关控制，群管理发送 `lssv` 即可查看功能模块的启用状态，使用以下命令进行控制：

```
启用 service-name
禁用 service-name
```


## 如何开始使用

如果您具备基本的linux与python能力，并拥有一台服务器（轻量级即可），您可以参阅部署指南自行部署。

部署完成后在群聊对bot发送以下命令开启对应功能：
- `启用 ba_calendar`
- （日服可选）`启用 ba_twitter`
- `ba(日,国,国际,en日,db日,db国际)服日历 on`
- `ba更新卡池`
- `@bot关注+up主名字或uid`，推荐关注列表如下

1. 夜猫咪喵喵猫(425535005)
2. 威威字幕君(7045822)
3. 碧蓝档案情报站(436037759)
4. 蔚蓝档案(3493265644980448)
  
## 开源协议及免责声明

本项目遵守GPL-3.0协议开源，请在协议允许的条件及范围内使用本项目。本项目的开发者不会强制向您索要任何费用，同时也不会提供任何质保，一切因本项目引起的法律、利益纠纷由与本项目的开发者无关。
- 对于自行搭建、小范围私用的非营利性bot，若遇到任何部署、开发上的疑问，欢迎提交issue或加入[开发交流群](https://jq.qq.com/?_wv=1027&k=6zyqKSqT)（如炸群请加备用群[星乃の5番灵装](https://jq.qq.com/?_wv=1027&k=WYcls71E)）讨论，我们欢迎有礼貌、描述详尽的提问！
- 对于以营利为目的部署的bot，由部署者负责，与本项目的开发者无关，本项目的开发者及社区没有义务回答您部署时的任何疑问。
- 对于HoshinoBot插件的开发者，在您发布插件或利用插件营利时，请遵守GPL-3.0协议将插件代码开源。

最终解释权归HoshinoBot开发组所有。




### 部署步骤

#### Windows 部署

1. 安装下面的软件/工具
    - [Python](https://www.python.org/downloads/windows/) 3.8(安装时必需勾选add python 3.8 to path)：https://www.python.org/downloads/release/python-3810/
    - Git：https://git-scm.com/download/win
      
如果安装了python 3.10，需要把requirements.txt中的`matplotlib~=3.2.1`改为`matplotlib~=3.5.2`，下面命令中的3.8也得改成3.10  

2. 下载整合包：https://github.com/Cosmos01/HoshinoBot_Blue/releases/download/release/HoshinoBot_Blue.zip

3. 解压后进入HoshinoBot_Blue，点击资源管理器左上角的 `文件 -> 打开Windows Powershell`，输入以下命令克隆本仓库并安装依赖
    ```powershell
    py -3.8 -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt`
    ```
    >若此处有报错信息，请务必解决，将错误信息复制到百度搜索一般即可找到解决办法。  

4. 回到资源管理器，进入`hoshino\config`文件夹，然后右键使用Edit with IDLE打开其中的`__bot__.py`，按照其中的注释说明进行编辑。

    > 如果您不清楚某项设置的作用，请保持默认。基本上把SUPERUSERS里面改成自己的qq号就行了。
5. 更新插件版本
     可以直接双击update.bat
     或是在hoshino\modules\Blue_Archive_HoshinoBot文件夹下打开Windows Powershell输入以下命令
     ```powershell
     git pull
     ```
6. 回到powershell输入以下命令或直接双击打开run.bat，启动 HoshinoBot

    ```powershell
    py -3.8 run.py
    ```

    > 若能看到日志`INFO: Running on 127.0.0.1:9090`，说明HoshinoBot启动成功。您可以忽略启动时的WARNING信息。如果出现ERROR，说明部分功能可能加载失败。

    至此，HoshinoBot的“大脑”已部署成功。接下来我们需要部署无头qq客户端，作为HoshinoBot的“口”和“耳”，收发消息。

7. 下载 go-cqhttp (推荐使用dev版本)至合适的文件夹

    - github 发布页：https://github.com/Mrs4s/go-cqhttp/releases
    - go-cqhttp dev版本(选个左边绿勾中间蓝字是dev的点进去就可以下了)：https://github.com/Mrs4s/go-cqhttp/actions/workflows/ci.yml

    > 您需要根据自己的机器架构选择版本，通常选择AMD64版本，

8. 启动go-cqhttp，选择反向 Websocket 通信，然后到生成的config.yml中修改配置：
    拉到最底下，将`servers:`下的内容替换为以下内容
    ```yaml
    servers:
      - ws-reverse:
          universal: ws://127.0.0.1:9090/ws/
          reconnect-interval: 5000
          middlewares:
            <<: *default
    ```

    > 你需要在资源管理器上方菜单 -> 查看 -> 显示/隐藏 中勾选"文件扩展名"，以修改文件的后缀名。
    
    将其中的“你的机器人QQ号”替换为实际的QQ号，通常为8~11位纯数字。密码留空使用扫码登录，你也可以将密码写入配置文件，此时请妥善保存您的配置文件，不要泄露给其他人。
    
    > 关于go-cqhttp的配置，你可以在[这里](https://docs.go-cqhttp.org/guide/config.html#%E9%85%8D%E7%BD%AE%E4%BF%A1%E6%81%AF)找到更多说明。

9. 启动go-cqhttp，按照提示登录。

    登陆成功后，私聊机器人发送`在？`，若机器人有回复，恭喜您，您已经成功搭建起HoshinoBot了！

    之后您可以尝试在群内发送`!帮助`以查看会战管理的相关说明，发送`help`查看其他一般功能的相关说明，发送`pcr速查`查看常用网址等。
    
    注意，此时您的机器人功能还不完全，部分功能可能无法正常工作。若希望您的机器人可以发送图片，或使用其他进阶功能，请参考本章**更进一步**的对应小节。



#### Linux 部署

> CentOS已停止更新，推荐使用Ubuntu 20.04或Debian。

1. 安装 Python 3.8和工具

    ```bash
    # Ubuntu or Debian
    sudo apt install python3.8
    sudo apt install unzip
    sudo apt install git
    ```

2. 下载整合包并安装依赖包
    ```bash
    wget https://github.com/Cosmos01/HoshinoBot_Blue/releases/download/release/HoshinoBot_Blue.zip
    unzip HoshinoBot_Blue.zip
    cd HoshinoBot_Blue
    python3.8 -m pip install -r requirements.txt
    ```

3. 编辑配置文件
    ```bash
    nano hoshino/config/__bot__.py
    ```
    > 配置文件内有相应注释，请根据您的实际配置填写，HoshinoBot仅支持反向ws通信
    >
    > 您也可以使用`vim`编辑器，若您从未使用过，我推荐您使用 `nano` : )

4. 更新版本
   ```bash
   cd hoshino/modules/Blue_Archive_HoshinoBot
   git pull
   ```

5. 运行HoshinoBot
    ```bash
    python3.8 run.py
    ```

    > 你需要在tmux或screen中运行。

6. 下载 go-cqhttp 至合适的文件夹

    - github 发布页：https://github.com/Mrs4s/go-cqhttp/releases

    > 您需要根据自己的机器架构选择版本，一般x86/64的Linux选择[go-cqhttp_linux_386.tar.gz](https://github.com/Mrs4s/go-cqhttp/releases/download/v1.0.0-rc1/go-cqhttp_linux_386.tar.gz)

7. 启动go-cqhttp，选择反向 Websocket 通信，然后到生成的config.yml中修改配置：
    拉到最底下，将`servers:`下的内容替换为以下内容

    ```yaml
    servers:
      - ws-reverse:
          universal: ws://127.0.0.1:9090/ws/
          reconnect-interval: 5000
          middlewares:
            <<: *default
    ```

    将其中的“你的机器人QQ号”替换为实际的QQ号，通常为8~11位纯数字。密码留空使用扫码登录，你也可以将密码写入配置文件，此时请妥善保存您的配置文件，不要泄露给其他人。

    > 关于go-cqhttp的配置，你可以在[这里](https://docs.go-cqhttp.org/guide/config.html#%E9%85%8D%E7%BD%AE%E4%BF%A1%E6%81%AF)找到更多说明。

8. 运行`go-cqhttp`，按照提示登录。

    登陆成功后，私聊机器人发送`在？`，若机器人有回复，恭喜您！您已经成功搭建起HoshinoBot了。之后您可以尝试在群内发送`!帮助`以查看会战管理的相关说明，发送`help`查看其他一般功能的相关说明，发送`pcr速查`查看常用网址等。

    注意，此时您的机器人功能还不完全，部分功能可能无法正常工作。若希望您的机器人可以发送图片，或使用其他进阶功能，请参考本章**更进一步**的对应小节。

### 更进一步

现在，机器人已经可以使用`会战管理`、`模拟抽卡(纯文字版)`等基本功能了。但还无法使用`竞技场查询`、`番剧订阅`、`推特转发`等功能。这是因为，这些功能需要对应的静态图片资源以及相应的api key。相应资源获取有难有易，您可以根据自己的需要去获取。

下面将会分别介绍资源与api key的获取方法：



#### 静态图片资源







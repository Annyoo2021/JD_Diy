## 使用方法
### 部署机器人
#### 方法一、 在容器中使用命令
```shell
rm -rf diybot.sh && wget https://ghproxy.com/https://raw.githubusercontent.com/Annyoo2021/JD_Diy/master/config/diybot.sh && bash diybot.sh
```
#### 方法二、 给机器人发消息
```text
/cmd rm -rf diybot.sh && wget https://ghproxy.com/https://raw.githubusercontent.com/Annyoo2021/JD_Diy/master/config/diybot.sh && bash diybot.sh
```
### V4BOT用户部署[user.py](https://github.com/Annyoo2021/JD_Diy/blob/master/jbot/user.py)
1. 进入容器，输入如下命令：`docker exec -it jd bash`
2. 把 [user.py](https://github.com/Annyoo2021/JD_Diy/blob/master/jbot/user.py) 下载到 `/jbot/diy` 目录下，输入如下命令：
```
cd /jd/jbot/diy && rm -rf user.py && wget https://ghproxy.com/https://raw.githubusercontent.com/Annyoo2021/JD_Diy/master/jbot/user.py && cd /jd/ && pm2 stop jbot && rm -rf user.session && python3 -m jbot
```
4. 输入手机号和 `telegram` 验证码进行登录后按 `Ctrl`+`C` 退出前台运行，不管出现任何情况，都继续执行第4步
5. 后台挂起机器人，输入如下命令：`pm2 start jbot`
### 青龙用户部署[user.py](https://github.com/Annyoo2021/JD_Diy/blob/master/jbot/user.py) 
1. 进入容器，输入如下命令：`docker exec -it qinglong bash`
2. 把 [user.py](https://github.com/chiupam/JD_Diy/blob/main/jbot/user.py) 下载到 `/jbot/diy` 目录下，输入如下命令：`cd /ql/jbot/diy;rm -rf user.py;wget https://raw.githubusercontent.com/Annyoo2021/JD_Diy/master/jbot/user.py;cd /ql/;ps -ef | grep "python3 -m jbot" | grep -v grep | awk '{print $1}' | xargs kill -9 2>/dev/null;rm -rf user.session;python3 -m jbot`
3. 输入手机号和 `telegram` 验证码进行登录后按 `Ctrl`+`C` 退出前台运行，不管出现任何情况，都继续执行第4步
4. 后台挂起机器人，输入命令：`nohup python3 -m jbot > /ql/log/bot/bot.log 2>&1 &`

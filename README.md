# vcc: the next generation of chat platform
## Introduction
Very cool chat (short form vcc) is a new way for chat which is faster, more secure, more open and powerful, you can’t live without it once you use it. 
There are 2 parts in vcc, including rpc (server and service) and gateways. 
## Usage (for a normal user)
You can easily use it using gateways. There are currently three official gateways designed for normal users: 
* web-vcc supports nearly all features, but it requires modern browsers and has poor support for mobile devices.
* vcc-godot supports fewer features,but it is much more friendly to mobile users.
* vos (vcc on ssh) is designed for new hackers, but it supports few features.
You can choose any of them to use.
## Usage (for anyone who wants to deploy in his own server)
### Install rpc
You need to do the following steps:
1. Install python>=3.10, you need to replace `python` with `python3` in the following commands if the default python is python2. 
2. Install minio and start it. (If you would like to have attachment support)
3. Run the following commands: 
```bash
git clone --depth 1 https://github.com/vcc-chat/vcc_rpc.git 
cd vcc_rpc
python -m venv env
. env/bin/activate
python -m pip install -r requirements.txt
nohup python server/main.py &
nohup python services/chat.py &
nohup python services/login.py &
nohup python services/bot.py &  # optional, only if you want bot support, you should also set some envs
nohup python services/file.py &  # optional, only if you want attachment support
#nohup python services/record.py & Not functional so far
```
### Install web-vcc & vcc_godot
```bash
git clone --depth 1 https://github.com/vcc-chat/web-vcc.git 
cd backend
python -m venv env
. env/bin/activate
pip install -r requirements.txt
nohup python main.py &
# TODO: nginx configuration
```
### Install vos
```bash
# TODO
```
### Install vcc-bot server
```bash
git clone --depth 1 https://github.com/vcc-chat/vcc-bot.git
cd vcc-bot/server
python -m venv env
. env/bin/activate.fish
pip install -r requirements.txt
nohup python main.py
```

### 1.download link

https://github.com/fatedier/frp/releases/download/v0.62.1/frp_0.62.1_linux_amd64.tar.gz
https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh
curl -L https://ollama.com/download/ollama-linux-amd64.tgz -o ollama-linux-amd64.tgz
----------
### 2.linux command

docker build -t qgisweb:1.0.0 .

1.生成公钥
ssh-keygen -t ed25519 -C "q30china@gmail.com"
2.将公钥~/.ssh/id_ed25519.pub内容添加到GitHub账户的SSH Keys设置中
3. 使用SSH URL重新克隆
git clone git@github.com:q30china/linux.git
----------
### 3.swap memory

1.确保无残留占用
sudo swapoff /home/user/swapfile 2>/dev/null
sudo rm -f /home/user/swapfile 
2.在独立分区 /home/user 创建Swap
sudo dd if=/dev/zero of=/home/user/swapfile bs=1G count=4
sudo chmod 600 /home/user/swapfile
sudo mkswap /home/user/swapfile
sudo swapon /home/user/swapfile

### 4.github related

0. 使用SSH URL克隆
git clone git@github.com:q30china/linux.git

1. 进入仓库目录
cd your-repo-name

2. 添加所有更改
git add .

3. 提交到本地
git commit -m "Add first script killsome to directory bat"

4. 推送到远程main分支（首次）
git push -u origin main

5. 更改推送之前
git pull

### 5.update ollama and openwebui

docker stop ""
docker pull ghcr.io/open-webui/open-webui:latest
docker rm ""
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:latest

curl -L https://ollama.com/download/ollama-linux-amd64.tgz -o ollama-linux-amd64.tgz
cd /home/user/tools/ollama
gunzip ollama-linux-amd64.tgz
tar xvf ollama-linux-amd64.tar
ollama serve

### 6.update snipe-it

cd /home/user/git/snipe-it
git pull
vi .env
```
# --------------------------------------------
# REQUIRED: DOCKER SPECIFIC SETTINGS
# --------------------------------------------
APP_VERSION=
APP_PORT=60001

# --------------------------------------------
# REQUIRED: BASIC APP SETTINGS
# --------------------------------------------
APP_ENV=production
APP_DEBUG=false
# Please regenerate the APP_KEY value by calling `docker compose run --rm app php artisan key:generate --show`. Copy paste the value here
APP_KEY= base64:g2WHulLyIcNUk8lONwmLWF/eEiu+vXz38LP62KnfyRM=
APP_URL=http://www.ginhai.com:60001
# https://en.wikipedia.org/wiki/List_of_tz_database_time_zones - TZ identifier
APP_TIMEZONE='UTC'
APP_LOCALE=en-US
MAX_RESULTS=500
```
docker compose up
docker compose down

### 7.python virtual enviroment 
source .venv/bin/activate
# 执行以下命令，检查Python路径是否指向.venv
python -c "import sys; print(sys.executable)"

### 8.dufs implement at ubuntu
#https://github.com/sigoden/dufs/releases/
tar -xzf  dufs-v0.40.0-x86_64-linux.tar.gz
./dufs --port 5000 --allow-upload /home/user/tools/share

### 9.Trojan 针对域名的3个月证书过期问题，证书申请（后台应该会自动申请，记录下时间2025.10.15看是否过期）

systemctl stop nginx
sudo systemctl stop trojan.service

sudo apt-get install certbot python3-certbot-nginx
sudo certbot --nginx -d www.ginhai.com

vi /etc/trojan/conf/server.json
    "cert": "/etc/letsencrypt/live/www.ginhai.com/fullchain.pem",
    "key": "/etc/letsencrypt/live/www.ginhai.com/privkey.pem", 

sudo systemctl start trojan.service
sudo systemctl status trojan.service

### 10.Wireguard相关，重启及其后，可能ipv4的转发没有自动打开，不知什么原因。以后如果有接受和放松，记得看服务器上ipv4转发

- /etc/wireguard/wg0.conf, 服务器中的MTU设置1400 > 客户端MTU 1300，warning错误不会再报，原来双方都设置1350

- /etc/sysctl.conf, net.ipv4.ip_forward = 1

- sysctl net.ipv4.ip_forward

- sysctl -p

### 12.

### 13.

### 14.

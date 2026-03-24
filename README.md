告别手动配置：Linux 实用脚本大全，覆盖系统、网络、Docker 与面板安装
以下是常用的 Linux 脚本和命令集合，涵盖 系统优化、网络管理、Docker 安装、VPS 维护 等用途。
🔧 系统优化 & 管理
1. 开启 Swap 虚拟内存

wget https://www.moerats.com/usr/shell/swap.sh && bash swap.sh

2. TCP 网络优化

wget http://sh.nekoneko.cloud/tools.sh -O tools.sh && bash tools.sh

3. 国内 DD 重装系统（Debian 12）

wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/leitbogioro/Tools/master/Linux_reinstall/InstallNET.sh' && chmod a+x InstallNET.sh && bash InstallNET.sh -debian 12 -pwd '你的密码'

4. NetCup VPS 硬盘扩容

growpart /dev/vda 3
resize2fs /dev/vda3

🌐 网络 & IP 管理
1. IP 解锁检测（流媒体/区域检测）

bash <(curl -sL IP.Check.Place)

或

bash <(curl -L -s check.unlock.media)

2. 解决 BandwagonHost (BWG) VPS DNS 解析问题
写入 DNS 配置

sudo tee /etc/resolv.conf <<EOF
nameserver 8.8.8.8
nameserver 1.1.1.1
nameserver 2001:4860:4860::8844
nameserver 2606:4700:4700::1111
EOF

锁定 DNS 配置（防止被修改）

sudo chattr +i /etc/resolv.conf

解锁 DNS 配置

sudo chattr -i /etc/resolv.conf

🛠️ 面板 & 工具
1. X-UI 面板安装（FranzKafkaYu 版）

bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/master/install.sh)

2. 3X-UI 面板安装（MHSanaei 版）

bash <(curl -Ls https://raw.githubusercontent.com/MHSanaei/3x-ui/refs/tags/v2.5.8/install.sh)

3. Docker 一键安装

curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh

4. 科技 Lion 脚本合集

curl -sS -O https://kejilion.pro/kejilion.sh && chmod +x kejilion.sh && ./kejilion.sh

5. 融合怪测试脚本（ECS 综合检测）

bash <(wget -qO- --no-check-certificate https://gitlab.com/spiritysdx/za/-/raw/main/ecs.sh)

6. 无痕网络测试（NodeQuality）

bash <(curl -sL https://run.NodeQuality.com)

📌 注意事项

    部分脚本需要 root 权限，建议使用 sudo -i 或 su root 切换至管理员运行。
    谨慎执行来源不明的脚本，建议先检查脚本内容再运行。
    部分脚本可能依赖 wget 或 curl，确保系统已安装：

yum install -y wget curl  # CentOS

# Debian/Ubuntu
apt install -y wget curl  

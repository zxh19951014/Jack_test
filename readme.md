# 服务器

## 账户与密码
* 合肥
    - 用户名 `ubuntu`
    - 密码 `zhongjia`
    - root密码 `zhongjia`
* 武汉
    - 用户名 `shenlanzj`
    - 密码 `zhongjia.123`
    - root密码 `zhongjia.123`
* 公司3090
    - 用户名 `ubuntu1804`
    - 密码 `zhongjia.123`
    - root密码 `zhongjia.123`
    - ip地址 `192.168.1.68`

## 安装软件 & 路径
+ frp(frpc, frps)： `/home/frp`
+ nginx
    - 合肥： `/usr/nginx`  
    - 武汉： `/etc/nginx?` (*忘记具体位置，其实不管用，已配置自启*)
    - 查找命令： `whereis nginx`
+ 向日葵： `/usr/login/sunlogin`

## 静态ip
* 合肥： `198.168.1.51`
* 武汉： 现在不是静态ip

## nginx
* 静态资源文件路径 `/home/zhongjia/myImage`
* 端口 `8089`
* 浏览器查看静态资源文件  
    *需要在局域网里其他电脑进行查阅*
    - 合肥： `ip：8089/image/`
    - 武汉： `ip：8089/image/`

## frp
* 客户端配置
    - 合肥端口 `7022`
    - 公司3090 `7122`
    - 武汉端口 `7222`
* 服务端配置
    - ip地址： `39.106.120.132`
    - 账号： `root`
    - 密码： `zhongjia.123`
    - 路径： `/usr/frp`
    - 配置文件路径： `/usr/frp/frps.ini`
* 查看frp运行状态
    - `http://39.106.120.132:7500/static/#/`
  
## ubuntu 1604更改静态ip
1. 查看网卡名字&ip地址 输入`ifconfig`，显示如下图所示：
![ifconfig](./ifconfig.png)
2. 修改网关文件 `sudo vim /etc/network/interfaces`
3. 输入如下代码，如图所示：
![ifconfig](./interfaces.png)
    ```
    auto enn4s0
    iface enp4s0 inet static
    address 192.168.1.51
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 211.167.230.100 223.5.5.5
    ```
4. 重启网络并刷新网关
    ```
    sudo systemctl restart networking
    sudo ip addr flush enp4s0
    ```
        
# 研发

## NLP 
* requirements
    - jieba
    - snownlp
    - textblob
* 文件路径(*我的电脑*)： `D：/工作记/2021.02/情感分析`

## 临时风格迁移
- **二十分钟左右出结果**
* 环境名称： tensor
    - `conda activate tensor`
* requirements
    - Python 3.7
    - Tensorflow 2.4
    - scipy & numpy
    - keras
    - matplotlib
* path (*我的电脑*)
    - `D：/工作记录/2021.04/GAT`
* use
    - `gat.ipynb`

## 风格迁移
* 环境名称： tf1
    - `conda activate tf1`
* requirements
    - Python 3.6
    - Tensorflow 1.12
    - scipy & numpy
    - keras
    - matplotlib
* path (*公司3090*)
    - `/home/ubuntu1804/work-project/2021.04/fast-style-transfer`
* train network
    - `python train_network.py --style <style image> --train-path <path to training images> --save-path <directory to save network>`
* fast style transfer
    - `python stylize_image.py --content <content image> --network-path <path to style network> --output-path <output image path>`

## 图像分割
* 环境名称： tf1
    - `conda activate tf1`
* requirements
    - python 3.6
    - keras
    - numpy & scipy
    - opencv
* path (*我的电脑*)
    - `D：/工作记录/2021.05/FCN-for-Semantic-Segmentation/`
* use
    - `FCN-8.ipynb`

## 小图合成大图
* 环境名称： tensor
    - `conda activate tensor`
* requirements
    - opencv
    - pillow
* path (*我的电脑*)
    - `D：/工作记录/2021.05/ceshi`
* use
    - `convert_image.py` 提取目录下所有图片,更改尺寸后保存到另一目录(需要统一尺寸)
    - `hecheng.py` 执行小图合成大图

## 素材
* path (*我的电脑*)
    - `D：/工作记录/深蓝`
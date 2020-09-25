虚拟私有网络的学习
---------------------------
# vpsSetting<br>
  私有网络的搭建可以提高自己的技术素养，<br>
#step 1: 境外服务器租赁<br>
  常用的服务器像`vultr`,`digitalocean`,`virmach`等都是不错的选择，在浏览器输入关键词即可进入官方网站，比较便宜的是`virmach`，cost最低是`2.25刀`一个月。进入官网之后，选择自己可以接受的不同价位，不同价位的配置不同，根据个人需要。<br>
#step 2: 配置服务器的ss服务<br>
  1）进入服务器的`terminal`；<br>
  2）安装`pip: sudo apt install python3-pip`<br>
  3）安装shadowsocks: `pip3 install https://github.com/shadowsocks/shadowsocks/archive/master.zip`<br>
  4）创建ss的配置文件：`vim /etc/shadowsocks.json`<br>
  5）编辑配置文件，在文件中输入如下代码：<br>
  {<br>
  `"server":"your_vps_ip",`<br>
  `"server_port":8388,`<br>
  `"local_address": "127.0.0.1",`<br>
  `"local_port":1080,`<br>
  `"password":"mypassword",`<br>
  `"timeout":300,`<br>
  `"method":"aes-256-cfb",`<br>
  `"fast_open": false`<br>
  }<br>
#step 3: <br>
  1）启动ss服务<br>
    `ssserver -c /etc/shadowsocks.json -d start`<br>
  2）关闭ss服务<br>
    `ssserver -c /etc/shadowsocks.json -d stop`<br>
#step 4:<br>
  在客户机，也就是你自己的电脑主机上安装shadowsocks软件，ip,port,密码，以及加密方式与上保持相同<br>

-----------------

  至此，一个属于自己的虚拟私有网络就有啦<br>


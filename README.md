# vpsSetting
这是一个搭建个人vps的教程，目的是自由访问互联网
#step 1: 境外服务器租赁
常用的服务器像vultr,digitalocean,virmach等都是不错的选择，在浏览器输入关键词即可进入官方网站，比较便宜的是virmach，cost最低是2.25刀一个月。进入官网之后，选择自己可以接受的不同价位，不同价位的配置不同，根据个人需要。
#step 2: 配置服务器的ss服务
1）进入服务器的terminal；
2）安装pip: sudo apt install python3-pip
3）安装shadowsocks: pip3 install https://github.com/shadowsocks/shadowsocks/archive/master.zip
4）创建ss的配置文件：vim /etc/shadowsocks.json
5）编辑配置文件，在文件中输入如下代码：
{
"server":"your_vps_ip",
"server_port":8388,
"local_address": "127.0.0.1",
"local_port":1080,
"password":"mypassword",
"timeout":300,
"method":"aes-256-cfb",
"fast_open": false
}
#step 3: 
1）启动ss服务
ssserver -c /etc/shadowsocks.json -d start
2）关闭ss服务
ssserver -c /etc/shadowsocks.json -d stop
#step 4: 在客户机，也就是你自己的电脑主机上安装shadowsocks软件，ip,port,密码，以及加密方式与上保持相同
#至此，vps配置完成，你已经有了自己的私有VPN，另外手机科学上网也可以使用shadowsocks的APP，配置同step4





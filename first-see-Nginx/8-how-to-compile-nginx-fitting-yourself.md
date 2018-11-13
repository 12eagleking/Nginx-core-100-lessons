# 编译Nginx

- （1）下载Nginx
- （2）介绍各目录
- （3）Configure
- （4）中间文件介绍
- （5）编译
- （6）安装

## 过程

### 1.打开nignx官网：`nginx.org`
![nginx官网](./img/8/nginxOfficialWebsite.jpg)
### 2.点击右侧`download`
![nginx官网](./img/8/nginxSourceCodeDownload.png)
### 3.下载源码
- 右键点击上图红圈中的`nginx-1.14.1`,选中**复制链接地址**
- 打开centos的bash，输入
```bash
wget http://nginx.org/download/nginx-1.14.1.tar.gz
```
![wgetNginx](./img/8/wgetNginx.png)

- 解压
```bash
tar -xzf nginx nginx-1.14.1.tar.gz  
```
![tarNginxGz](./img/8/tarNginxGz.png)
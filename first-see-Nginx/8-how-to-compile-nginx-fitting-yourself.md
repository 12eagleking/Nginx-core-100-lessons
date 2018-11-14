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

> [nginx源码目录](./8-nginx-source-file.md/#Nginx源码目录)

- 编译
    - 编译前看看configure支持哪些参数（`./configure --help`）
        - 第一类：nginx执行中会去找哪些目录中下的文件作为它的辅助文件
        ![nginx-configure-help-1](./img/8/nginx-configure-help-1.png)
            - `--modules-path=PATH`：使用动态模块；`--lock-path=PATH`:确定nginx.lock文件在的路径；没有任何变动，只需要指定`--prefix=PATH`(所有其他的这类文件会在prefix目录下建相应的文件夹)
        - 第二类：
        ![nginx-configure-help-2](./img/8/nginx-configure-help-2.png)
            - with（默认不会编译进nginx）和without（默认编译进nginx）
        - 第三类：指定了nginx编译中需要的一些特殊参数
        ![nginx-configure-help-3](./img/8/nginx-configure-help-3.png)
    
    - 实际编译nginx：
        - 1.用默认参数
        `./configure --prefix=/home/nginx-test/nginx`
            > error:

            ![configure-prefix-error-pcre1](./img/8/configure-prefix-error-pcre1.png)

            - #### 解决：`yum install pcre`,再configure，出错：

            ![configure-prefix-error-pcre2](./img/8/configure-prefix-error-pcre2.png)

            - #### 解决：`yum install pcre-devel`,再configure，出错：

            ![configure-prefix-error-zlib1](./img/8/configure-prefix-error-zlib1.png)

            - #### 解决：`yum install -y zlib-devel`,再configure,OK！

            ![configure-prefix-OK](./img/8/configure-prefix-OK.png)
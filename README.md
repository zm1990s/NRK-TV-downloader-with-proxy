English
=================

中文说明往下翻。。

NRK-downloader-with-proxy-CLI
====

This is a set of scripts help you to download subtitles and videos from tv.nrk.no

scripts orginally written by [Ingvar Hagelund](http://users.linpro.no/ingvar/nrk/)

The author has written a blog about the scripts in [here](http://ingvar.blog.redpill-linpro.com/2012/05/31/downloading-hd-content-from-tv-nrk-no/comment-page-1/)

you can find the original scripts in [here](http://users.linpro.no/ingvar/nrk/)

The scipts rely on AdobeHDS, you can find the newest version of it in [here](https://raw.githubusercontent.com/K-S-V/Scripts/master/AdobeHDS.php)

And I made some modification so it can support http proxy 

and written a scripts for NRK Radios

**Usage:** ` ./nrk-download "URL-to-tv.nrk" [-p [proxy-address:port] ]`

**syntax description:**

      -p : means use http proxy, it's optional.
      
      proxy-address:port : 
      
      manually assign the proxy address instead of using the default '127.0.0.1:8087', 
      
      you can leave this blank that'll means use the default 127.0.0.1:8087.

**Examples:** `./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5`

or 	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p 127.0.0.1:2089`

or	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p`

**nrk-radio-download is for NRK radio only**

**the usage is the same as nrk-download**

NRK-downloader-GUI
====

Well, for those GUI-like users, I've written those scripts using system's dialog program, like zenity(for gnome) and kdialog(for kde).

all you need to do is make `install.sh` executable and then run it

    chmod +x install.sh
    ./install.sh
    
it's all install necessary files into some hidden folder(~/.nrk-download) in your Home directory and create a shortcut in Home directory

you can simply run `nrk-download.desktop` to launch the scipt and, that's it, enjoy it

Oh, on your first run it'll ask you whether you want to use http proxy or not (if you are using VPN, or can connect to nrk.no without proxy, you can choose `no` )

and, you have to select a **default download folder**

**Dependences**

_Fedora:_
*  php
*  php-bcmath
*  perl-DateTime-Precise
*  perl-Text-Iconv
*  perl-HTML-TokeParser-Simple
*  perl-libwww-perl

_Debian/Ubuntu:_
*  php5-cli
*  php5-curl
*  libwww-perl
*  libtext-iconv-perl
*  libhtml-tokeparser-simple-perl
*  libdatetime-precise-perl (cpan module - no .deb available, try running 'dh-make-perl --build --cpan DateTime::Precise' )


中文
=================

NRK-downloader-with-proxy-CLI
====

此项目是几个下载 nrk TV/Radio 的脚本，可用于Linux，按理说应该可以运行在Mac OS 上，只要安装需要的环境。

脚本原作是： [Ingvar Hagelund](http://users.linpro.no/ingvar/nrk/) ，个人只做了一点修改和优化

原作者写过一个博客专门介绍他的脚本，请看 [这里](http://ingvar.blog.redpill-linpro.com/2012/05/31/downloading-hd-content-from-tv-nrk-no/comment-page-1/)

源脚本可以在 [这里](http://users.linpro.no/ingvar/nrk/) 查看

脚本依赖于 AdobeHDS, 可以在 [这里](https://raw.githubusercontent.com/K-S-V/Scripts/master/AdobeHDS.php) 找到最新版

我做了些修改，使其支持http代理（常用的就是Goagent 代理）


**功能简介**

项目总共四个脚本，AdobeHDS.php 和 nrk-subtitles 两个是依赖，只需要下载和其他脚本放一起即可。

平时使用的是 nrk-download 和 nrk-radio-download， nrk-download 就是专门用来下nrk TV的（也可以用来下radio，只是牵扯到点小问题）。nrk-radio-download用来专门下载Radio的

以上两脚本都会下载`视频/音乐`文件到同名文件夹中，同时下载节目的封面（一般NRK节目都有封面的），nrk-download 会下载字幕（挪威语），而nrk-radio-download 会下载曲目列表（txt文件，如果Radio不存在播放列表就没有txt文件）。

这就是nrk-download 和 nrk-radio-download的唯一区别，`一个会下电视的字幕，一个会下载播放列表`


**使用方法:** ` ./nrk-download "URL-to-tv.nrk" [-p [代理ip:代理端口] ]`

` ./nrk-radio-download "URL-to-tv.nrk" [-p [代理ip:代理端口] ]`

**参数说明：**

      -p : 是个可选项，如果加上代表使用http代理，不加就不使用http代理（ **如果你用的VPN那就无需加了** ）
      
      代理ip:代理端口 : 这又是 -p 的一个可选项，即你可以单独用 `-p` 参数，也可以在 -p 后面加上你代理服务器的 `ip地址和端口号`
      
      如果只使用-p，即代表使用Goagent 的代理设置，即服务器地址和端口为：'127.0.0.1:8087', 会用Goagent的都清楚
      
      如果你用的不是 goagent 代理，那就需要指定其他代理用的 ip 和端口了，我没用过别的没法距离，使用 IP:端口 的形式就好了

**示例：** `./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5`

如果你用的是vpn，那就直接 ./脚本名+URL 执行

或	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p`

如果你用的Goagent ，那直接 ./脚本名+ URL + -p  执行

或	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p 127.0.0.1:2089`

如果使用其他HTTP代理， ./脚本名+ URL + -p + 代理ip：代理端口 执行

**nrk-radio-download用法和nrk-download 用法一样**

NRK-downloader-GUI
====

上面纯命令行已经能用了，为了照顾小白用户，特地利用系统对话框程序写了个界面，然后做个脚本整合，然后各种错误/依赖提醒，这样缺点是就只能用于Linux了，将KDE和Gnome的对话框写到了一起，自动识别

将两个脚本整合到一起，既能下TV又能下载Radio（不过检测过程会增多，速度会慢一点点）。

首次运行会提示用户是否使用代理，让用户选择默认下载文件夹（必须选择）

下载完发系统通知。

文件夹中有个`install.sh` 建议直接给这个脚本赋予运行权限，然后执行安装即可。安装后会在家目录创建一个`nrk-download.desktop`快捷方式

    chmod +x install.sh
    ./install.sh

**依赖**

_Fedora:_
*  php
*  php-bcmath
*  perl-DateTime-Precise
*  perl-Text-Iconv
*  perl-HTML-TokeParser-Simple
*  perl-libwww-perl

_Debian/Ubuntu:_
*  php5-cli
*  php5-curl
*  libwww-perl
*  libtext-iconv-perl
*  libhtml-tokeparser-simple-perl
*  libdatetime-precise-perl (cpan module - no .deb available, try running 'dh-make-perl --build --cpan DateTime::Precise' )
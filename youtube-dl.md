youtube-dl下载工具
=================


## 常规命令
> youtube-dl --update  //升级
> youtube-dl --help //帮助
> youtube-dl --version //查看版本


## 下载一个包含url地址文件
> -q 安静的下载    
> -c 强制恢复部分下载的文件  
> -w 覆盖已经存在的文件  
> -i 不理会错误  
> --no-playlist 不下载视频列表  
> -o 指定输出文件名  
> --simulate 模拟下载  
> -a file.txt  指定包含url的文件  
 
```bash
youtube-dl -ciw --no-playlist -o "%(title)s-%(id)s.%(ext)s" --simulate -a ./down.txt

youtube-dl -ciwq --no-playlist -o "%(title)s-%(id)s.%(ext)s" -a ./down.txt
```

## youtube.com取得下载链接
在播放页面注入jquery:

```javascript
document.getElementsByTagName('head')[0].appendChild(document.createElement('script')).setAttribute('src','https://code.jquery.com/jquery-1.9.1.min.js');
```

取得播放地址:
```javascript
$(".yt-uix-scroller-scroll-unit a").each(function(index, item){console.log(item.href);});

$("ytd-playlist-panel-video-renderer a").each(function(index, item){console.log(item.href);});
```

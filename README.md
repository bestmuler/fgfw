# v2ray+nginx+ws+TLS+fs实现操翻gfw效果

嫌麻烦就用[233脚本](https://github.com/233boy/v2ray)，选[4]，也就是ws+TLS，一路回车到底，用bt开个站点，装好https，网站设置里server节点加一段

``` bash
location / {
		#ws监听的回环端口
		#不清楚的，cat /etc/v2ray/config.json
		#看一下inbounds port
		proxy_pass http://127.0.0.1:56000; 
		proxy_http_version 1.1;
		proxy_set_header Upgrade $http_upgrade;
		proxy_set_header Connection "upgrade";
		proxy_set_header Host $http_host;
}
```

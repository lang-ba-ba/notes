# NGINX能够 
### - A HTTP server
### - Reverse proxy server
### - Load Balancer
### - Mail proxy server
### - HTTP cache
### - 更多...
# 为什么NGINX
### 可以处理更多的并发相比较于Apache
### 广泛的应用在各工业领域
### 高可用和高扩展的架构
### 独立线程处理多链接
# 润 
- `sudo pacman -S NGINX`
- `sudo systemctl status nginx`
- `curl localhost`
- `cd /etc/nginx`
- `cat nginx.conf`
- go through it, user, log, include conf file
- cd sites-enabled/
- ls ltr
- `unlink default`
- cd ../conf.d/
- nvim langbaba.local.conf
`server {
	listen 80 default_server;
	index index.html index.htm index.php;
	server_name langbaba.local;
	root /var/www/langbaba.local;
}`
- `nginx -t`
- cd /var/www/html/
- cd ../
- mkdir langbaba.local
- nvim index.html : Welcome to langbaba website powered by nginx
- systemctl reload nginx
- nvim langbaba.local.conf

- `server {
location / {
	try_files $uri $uri/ $uri.html =400;
}
location /foo {
	try_files $uri /foo.html;
}
}`
- nginx -t
- systemctl reload nginx
- nvim langbaba.local.conf
- server {
	error_page 400 404 /400.html;
	location = /400.html {
	internal;
	}
}
}
- nvim langbaba.local.conf
server {
	location /500error {
	fastcgi_pass Unix:/this/is/error;
	}

error_page 500 502 /50x.html;
	location = /50x.html {
	internal;
	}

}


###DOCKER NGINX REVERSE PROXY

Add new conf

```
vim conf/newconfig.conf

server {
    listen              80;
    listen              [::]:80;
    server_name         yourservername.com;
    access_log          /var/log/nginx/access.log;

    location / {
      proxy_pass http://your-ip:port;
      proxy_redirect http://your-ip:8080 http://yourservername.com;
    }
}
```

Add new servername in /etc/hosts
```
vim /etc/hosts

your-ip yourservername.com
```

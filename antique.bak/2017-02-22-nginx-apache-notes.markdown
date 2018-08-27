停止apache服务：

``` bash
$ sudo /etc/init.d/apache2 stop
```

或者

``` bash
$ sudo apache2ctl stop
```

取消apache自启动：

``` bash
$ sudo update-rc.d -f apache2 remove
```

恢复自启动则需要

``` bash
$ sudo update-rc.d apache2 defaults
```

Nginx启动与关闭，也是多种方式

```bash
//To stop your web server, you can type:
$ sudo systemctl stop nginx
//To start the web server when it is stopped, type:
$ sudo systemctl start nginx
//To stop and then start the service again, type:
$ sudo systemctl restart nginx
//If you are simply making configuration changes, Nginx can often reload without dropping connections. To do this, this command can be used:
$ sudo systemctl reload nginx
//By default, Nginx is configured to start automatically when the server boots. If this is not what you want, you can disable this behavior by typing:
$ sudo systemctl disable nginx
//To re-enable the service to start up at boot, you can type:
$ sudo systemctl enable nginx
```

或者

```bash
sudo /etc/init.d/nginx restart
sudo service nginx restart
```

补充：
macOS下面的nginx重启：

```bash
$ nginx -s reload
```

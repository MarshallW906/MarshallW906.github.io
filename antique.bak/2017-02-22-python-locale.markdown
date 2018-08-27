$ pip install shadowsocks

会出现类似如下错误

Traceback (most recent call last):
File "/usr/bin/pip", line 11, in <module>
sys.exit(main())
File "/usr/lib/python2.7/dist-packages/pip/__init__.py", line 215, in main
locale.setlocale(locale.LC_ALL, '')
File "/usr/lib/python2.7/locale.py", line 581, in setlocale
return _setlocale(category, locale)
locale.Error: unsupported locale setting

解决方法：

$ export LC_ALL=C

再次执行时报错消失。

------------------------分割线------------------------

报错消失之后再次执行pip会提示需要升级。升级之后遇到新问题，如下：

继续运行pip install shadowsocks时提示需要安装setuptools

应提示

$ sudo apt install python-setuptools -y

安装完之后问题解决。
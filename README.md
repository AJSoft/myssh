autossh使用帮助

verion:1.3
modifed:2012-10-17
1.修复使用重用同一个连接配置导致无法进行连接的问题。

verion:1.2
modifed:2012-09-05
1.修复1.1无法使用其他参数的bug
2.修复短nickname导致的错误，默认执行查找到的第一个
3.支持无密码添加，以及快捷连接

version:1.1
modified:2012-09-04
修改支持<nickname>/<server>，简化-l参数的使用。
	autossh <nickname>/<server>

version:1.0
modified:2012-08-31

Usage: -l <hostinfo> [more options]
  Available options
    -l : link host name
    -h : host list
    -s : search hostinfo
    -a : add new hostinfo
    	Usage: <nickname> <server> <port> <username> <passwd>

安装autossh：
	在控制台下切换到解压目录执行：./install.sh
	如果提示没有权限执行：chmod +x install.sh

新增连接列表:
	autossh -a <nickname> <server> <port> <username> <passwd>
	也可以直接修改 ~/.ssh/ssh_passwd 进行新增。
	注意：有格式要求需要格式正确。

显示所有连接列表：
	autossh -h

查询连接：
	autossh -s <nickname>/<server>
	使用nickname和server都可以进行查询。

连接服务器：
	autossh -l <nickname>/<server>
	使用nickname和server都可以进行连接。

FAQ：
	F：支持什么环境？
	Q：仅支持mac系统，理论上也支持linux但未进行测试，如果linux下有错自行修改配置文件。

	F：连接系统后出现乱码？
	Q：本地mac下编码与服务器不一致导致，修改终端-->偏好设置-->高级-->多语言环境，修改为服务器上编码。
		查看服务器编码：在服务器上执行 locale 即可。
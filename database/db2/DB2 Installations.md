# DB2 Installation on Linux

- 安装```DB2```1管理服务器
	进入解压目录，运行```./db2_install```，命令执行完```DB2```管理服务器就已经安装好了
	
- 创建用户组```db2iadm1```及用户```db2inst1```(密码也为```db2inst1```)
	依次执行：
	```groupadd -g 2000 db2iadm1```
	```useradd -m -g db2iadm1 -d /home/db2inst1 db2inst1```
	```passwd db2inst1``` 将改用户密码设置为 ```db2inst1```

- 创建实例
	```/opt/ibm/db2/V10.1/instance/db2icrt -u  db2inst1 db2inst1```

> **提示：**接下来切到```db2inst1```用户操作。

- 启动管理服务器
	```db2admin start```

- 启动实例
	```db2start```

<pre name="code" class="html">

平常大家做开发的时候电脑装的工具多了不方便管理.
所以写了一个bat脚本大家有需要的可以复制也可以fork自己去改.
添加到开始菜单栏或者桌面都是不错的.

@ECHO off
TITLE Switch %date% %time%  欢迎使用
:A
color A
CLS
ECHO                  ++++++++++++++++++++++++++++++++++++++++++++++++
ECHO                  =          WELCOME  TO  MY  SCRIPT !           =
ECHO                  =  启动Oracle服务菜单 = 1                      =
ECHO                  =  启动SqlServer服务菜单= 2                    =
ECHO                  =  启动MySql服务菜单 = 3                       =
ECHO                  =  启动虚拟机服务菜单 = 4                      =
ECHO                  =  进入Nginx菜单选项 = 5                       =
ECHO                  =  进入FileZilla菜单选项 = 6                   =
ECHO                  =  开启苹果服务单选项 = 9                      =
ECHO                  =  进入IpConfig服务菜单 = 10                   =
ECHO                  =  进入MongoDB Redis服务菜单 = 11              =
ECHO                  ++++++++++++++++++++++++++++++++++++++++++++++++
ECHO.
ECHO.
SET session=&quot;&quot;
SET /p session=Select[1/2/3/4/5/6/7/8/9/10/11]:
if /i &quot;%session%&quot;==&quot;0&quot; (goto:0)
if /i &quot;%session%&quot;==&quot;1&quot; (goto:1)
if /i &quot;%session%&quot;==&quot;2&quot; (goto:2)
if /i &quot;%session%&quot;==&quot;3&quot; (goto:3)
if /i &quot;%session%&quot;==&quot;4&quot; (goto:4)
if /i &quot;%session%&quot;==&quot;5&quot; (goto:5)
if /i &quot;%session%&quot;==&quot;6&quot; (goto:6)
if /i &quot;%session%&quot;==&quot;9&quot; (goto:9)
if /i &quot;%session%&quot;==&quot;10&quot; (goto:10)
if /i &quot;%session%&quot;==&quot;11&quot; (goto:11)

:0
CLS
@ECHO 谢谢使用...
ping 127.0.0.1 /n 3
exit



:1
@ECHO 进入Oracle菜单选项
@ECHO off
TITLE  Oracle 管理程序 %date% %time% 
:ORACLEMENU 
CLS 
ECHO. 
ECHO. * * Oracle 管理程序  *  
ECHO. * Oracle 进程 List   *  
taskList|findstr /i /b &quot;oracle&quot;
taskList|findstr /i /b &quot;tnslsnr&quot;
ECHO. 
    ECHO.  [1] 启动Oracle
    ECHO.  [2] 关闭Oracle
    ECHO.  [3] 重启Oracle
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET OracleSession=&quot;&quot;
SET /p OracleSession=Select[1/2/3/4]:
	IF /i &quot;%OracleSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%OracleSession%&quot;==&quot;1&quot; (goto:startOracle) 
    IF /i &quot;%OracleSession%&quot;==&quot;2&quot; (goto:stopOracle) 
    IF /i &quot;%OracleSession%&quot;==&quot;3&quot; (goto:restartOracle) 
    IF /i &quot;%OracleSession%&quot;==&quot;4&quot; (goto:back)
:back 
    GOTO:A
	ping 127.0.0.1 /n 3
:startOracle 
    CALL :startOracleServer
    GOTO ORACLEMENU
:stopOracle 
    CALL :shutdownOracle
    GOTO ORACLEMENU
:restartOracle 
    CALL :shutdownOracle
    CALL :startOracleServer
    GOTO ORACLEMENU
:shutdownOracle
    @ECHO &quot;正在关闭Oracle相关开机服务...&quot;
	NET STOP &quot;OracleOraDb11g_home1TNSListener&quot;
	NET STOP &quot;OracleServiceORCL&quot;
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startOracleServer
    @ECHO &quot;正在启动Oracle相关开机服务...&quot;
	NET START &quot;OracleServiceORCL&quot;
	NET START &quot;OracleOraDb11g_home1TNSListener&quot;
	@ECHO &quot;服务启动完毕!&quot;
	@ECHO &quot;检测监听状态&quot;
	lsnrctl status
	ping 127.0.0.1 /n 3
	@ECHO &quot;检测服务状态&quot;
	tnsping orcl
	ping 127.0.0.1 /n 3
	GOTO ORACLEMENU
	
	

:2
@ECHO 进入SqlServer菜单选项
@ECHO off
TITLE  SqlServer 管理程序 %date% %time% 
:SQLSERVERMENU 
CLS 
ECHO. 
ECHO. * * SqlServer 管理程序  *  
ECHO. * SqlServer 进程 List   *  
taskList|findstr /i /b &quot;sqlservr&quot;
ECHO. 
    ECHO.  [1] 启动SqlServer
    ECHO.  [2] 关闭SqlServer
    ECHO.  [3] 重启SqlServer
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET SqlServerSession=&quot;&quot;
SET /p SqlServerSession=Select[1/2/3/4]:
	IF /i &quot;%SqlServerSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%SqlServerSession%&quot;==&quot;1&quot; (goto:startSqlServer) 
    IF /i &quot;%SqlServerSession%&quot;==&quot;2&quot; (goto:stopSqlServer) 
    IF /i &quot;%SqlServerSession%&quot;==&quot;3&quot; (goto:restartSqlServer) 
    IF /i &quot;%SqlServerSession%&quot;==&quot;4&quot; (goto:back)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:startSqlServer 
    CALL :startSqlServers
    GOTO SQLSERVERMENU
:stopSqlServer 
    CALL :shutdownSqlServer
    GOTO SQLSERVERMENU
:restartSqlServer 
    CALL :shutdownSqlServer
    CALL :startSqlServers
    GOTO SQLSERVERMENU
:shutdownSqlServer
    @ECHO &quot;正在关闭SqlServer相关开机服务...&quot;
	NET STOP &quot;MSSQLSERVER&quot;
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startSqlServers
    @ECHO &quot;正在启动SqlServer相关开机服务...&quot;
	NET START &quot;MSSQLSERVER&quot;
	ECHO 服务启动完毕!
	ping 127.0.0.1 /n 3
	GOTO SQLSERVERMENU
	
	
:3
@ECHO 进入MySQL菜单选项
@ECHO off
TITLE  MySQL 管理程序 %date% %time% 
:MYSQLMENU 
CLS 
ECHO. 
ECHO. * * MySQL 管理程序  *  
ECHO. * MySQL 进程 List   *  
taskList|findstr /i /b &quot;mysql&quot;
ECHO. 
    ECHO.  [1] 启动MySQL
    ECHO.  [2] 关闭MySQL
    ECHO.  [3] 重启MySQL
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET MySQLSession=&quot;&quot;
SET /p MySQLSession=Select[1/2/3/4]:
	IF /i &quot;%MySQLSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%MySQLSession%&quot;==&quot;1&quot; (goto:startMySQL) 
    IF /i &quot;%MySQLSession%&quot;==&quot;2&quot; (goto:stopMySQL) 
    IF /i &quot;%MySQLSession%&quot;==&quot;3&quot; (goto:restartMySQL) 
    IF /i &quot;%MySQLSession%&quot;==&quot;4&quot; (goto:back)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:startMySQL 
    CALL :startMySQLServer
    GOTO MYSQLMENU
:stopMySQL 
    CALL :shutdownMySQL
    GOTO MYSQLMENU
:restartMySQL 
    CALL :shutdownMySQL
    CALL :startMySQLServer
    GOTO MYSQLMENU
:shutdownMySQL
    @ECHO &quot;正在关闭MySQL相关开机服务...&quot;
	NET STOP &quot;MySQL&quot;
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startMySQLServer
    @ECHO &quot;正在启动MySQL相关开机服务...&quot;
	NET START &quot;MySQL&quot;
	ECHO 服务启动完毕!
	ping 127.0.0.1 /n 3
	GOTO MYSQLMENU
	
	

:4
@ECHO 进入VMware菜单选项
@ECHO off
TITLE  VMware 管理程序 %date% %time% 
SET VMWARE_PATH=D:
SET VMWARE_DIR=D:\Program Files\VMware\
:VMWAREMENU 
CLS 
ECHO. 
ECHO. * * VMware 管理程序  *  
ECHO. 
ECHO. * VMware 进程 List   *  
taskList|findstr /i /b &quot;vm&quot;
ECHO. 
    ECHO.  [1] 启动VMware
    ECHO.  [2] 关闭VMware
    ECHO.  [3] 重启VMware
	ECHO.  [4] 启动VMware界面
    ECHO.  [5] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET VMwareSession=&quot;&quot;
SET /p VMwareSession=Select[1/2/3/4/5]:
	IF /i &quot;%VMwareSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%VMwareSession%&quot;==&quot;1&quot; (goto:startVMware) 
    IF /i &quot;%VMwareSession%&quot;==&quot;2&quot; (goto:stopVMware) 
    IF /i &quot;%VMwareSession%&quot;==&quot;3&quot; (goto:restartVMware) 
	IF /i &quot;%VMwareSession%&quot;==&quot;4&quot; (goto:startVMwareexe) 
    IF /i &quot;%VMwareSession%&quot;==&quot;5&quot; (goto:back)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:startVMware 
    CALL :startVMwareServer
    GOTO VMWAREMENU
:stopVMware 
    CALL :shutdownVMware
    GOTO VMWAREMENU
:restartVMware 
    CALL :shutdownVMware
    CALL :startVMwareServer
    GOTO VMWAREMENU
:shutdownVMware
    @ECHO &quot;正在关闭VMware相关开机服务...&quot;
	NET STOP &quot;VMwareHostd&quot;
	NET STOP &quot;VMAuthdService&quot;
	NET STOP &quot;VMnetDHCP&quot;
	NET STOP &quot;VMware NAT Service&quot;
	NET STOP &quot;VMUSBArbService&quot;
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startVMwareServer
    @ECHO &quot;正在启动VMware相关开机服务...&quot;
	NET START &quot;VMwareHostd&quot;
	NET START &quot;VMAuthdService&quot;
	NET START &quot;VMnetDHCP&quot;
	NET START &quot;VMware NAT Service&quot;
	NET START &quot;VMUSBArbService&quot;
	ECHO 服务启动完毕!
	ping 127.0.0.1 /n 3
	GOTO VMWAREMENU
:startVMwareexe
    ECHO. 
    ECHO.启动VMware...... 
    IF NOT EXIST &quot;%VMWARE_DIR%vmware.exe&quot; ECHO &quot;%VMWARE_DIR%vmware.exe&quot;不存在 
    %VMWARE_PATH% 
    cd &quot;%VMWARE_DIR%&quot; 
    IF EXIST &quot;%VMWARE_DIR%vmware.exe&quot; (
        ECHO &quot;start '' vmware.exe&quot;
        start &quot;&quot; vmware.exe
    )
    ECHO.OK
	GOTO VMWAREMENU
	
	
	
:5
@ECHO 进入Nginx菜单选项
@ECHO off
TITLE Nginx 管理程序 %date% %time% 
CLS 
SET NGINX_PATH=D:
SET NGINX_DIR=D:\tools\nginx\
:NGINXMENU 
CLS 
ECHO. 
ECHO. * * Nginx 管理程序  *  
ECHO. 
ECHO. * Nginx 进程 List   *  
taskList|findstr /i &quot;nginx.exe&quot;
ECHO. 
    ECHO.  [1] 启动Nginx  
    ECHO.  [2] 关闭Nginx  
    ECHO.  [3] 重启Nginx  
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET NginxSession=&quot;&quot;
SET /p NginxSession=Select[1/2/3/4]:
	IF /i &quot;%NginxSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%NginxSession%&quot;==&quot;1&quot; (goto:startNginx) 
    IF /i &quot;%NginxSession%&quot;==&quot;2&quot; (goto:stopNginx) 
    IF /i &quot;%NginxSession%&quot;==&quot;3&quot; (goto:restartNginx) 
    IF /i &quot;%NginxSession%&quot;==&quot;4&quot; (goto:back)
:back
	CLS
    goto:A
	ping 127.0.0.1 /n 3
:startNginx 
    CALL :startNginxServer
    GOTO NGINXMENU
:stopNginx 
    CALL :shutdownNginx
    GOTO NGINXMENU
:restartNginx 
    CALL :shutdownNginx
    CALL :startNginxServer
    GOTO NGINXMENU
:shutdownNginx
    ECHO. 
    ECHO.关闭NginxServer...... 
    taskkill /F /IM nginx.exe &gt; nul
    ECHO.OK,关闭所有nginx.exe 进程
    GOTO: EOF
:startNginxServer
    ECHO. 
    ECHO.启动NginxServer...... 
    IF NOT EXIST &quot;%NGINX_DIR%nginx.exe&quot; ECHO &quot;%NGINX_DIR%nginx.exe&quot;不存在 
    %NGINX_PATH% 
    cd &quot;%NGINX_DIR%&quot; 
    IF EXIST &quot;%NGINX_DIR%nginx.exe&quot; (
        ECHO &quot;start '' nginx.exe&quot;
        start &quot;&quot; nginx.exe
    )
    ECHO.OK
	GOTO NGINXMENU
	
	
:6
@ECHO 进入FileZilla菜单选项
@ECHO off
TITLE FileZilla 管理程序 %date% %time% 
CLS 
SET FZ=D:
SET FZ_SERVER=&quot;D:\Program Files (x86)\FileZilla Server&quot;
SET FZ_CLIENT=&quot;D:\Program Files (x86)\FileZilla FTP Client&quot;
:FILEZILLAMENU 
CLS 
ECHO. 
ECHO. * * FileZilla 管理程序  *  
ECHO. 
ECHO. * FileZilla 进程 List   *  
taskList|findstr /i /b &quot;FileZilla Server.exe&quot;
ECHO. 
    ECHO.  [1] 启动FileZilla  
    ECHO.  [2] 关闭FileZilla  
    ECHO.  [3] 重启FileZilla  
	ECHO.  [4] 启动FileZilla服务端接口 
	ECHO.  [5] 启动FileZilla客户端 
    ECHO.  [6] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET FileZillaSession=&quot;&quot;
SET /p FileZillaSession=Select[1/2/3/4/5/6]:
	IF /i &quot;%FileZillaSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%FileZillaSession%&quot;==&quot;1&quot; (goto:startServer) 
    IF /i &quot;%FileZillaSession%&quot;==&quot;2&quot; (goto:stopServer) 
    IF /i &quot;%FileZillaSession%&quot;==&quot;3&quot; (goto:restartServer) 
	IF /i &quot;%FileZillaSession%&quot;==&quot;4&quot; (goto:startServerInterface)
	IF /i &quot;%FileZillaSession%&quot;==&quot;5&quot; (goto:startClientTools)
    IF /i &quot;%FileZillaSession%&quot;==&quot;6&quot; (goto:back)
:back
	CLS
    goto:A
	ping 127.0.0.1 /n 3
:startServer 
    CALL :startFileZillaServer
    GOTO FILEZILLAMENU
:stopServer 
    CALL :shutdownFileZillaServer
    GOTO FILEZILLAMENU
:restartServer 
    CALL :shutdownFileZillaServer
    CALL :startFileZillaServer
    GOTO FILEZILLAMENU
:shutdownFileZillaServer
    ECHO. 
    ECHO.关闭FileZilla...... 
    NET STOP &quot;FileZilla Server&quot;
    ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startFileZillaServer
    ECHO. 
    ECHO.启动FileZilla Server...... 
    NET START &quot;FileZilla Server&quot;
	ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO FILEZILLAMENU
:startServerInterface 
    ECHO. 
    ECHO.启动FileZilla Server Interface...... 
    IF NOT EXIST %FZ_SERVER%&quot;FileZilla Server Interface.exe&quot; ECHO &quot;%FZ_SERVER%FileZilla Server Interface.exe&quot;不存在 
    %FZ% 
    cd &quot;%FZ_SERVER%&quot; 
    IF EXIST &quot;%FZ_SERVER%FileZilla Server Interface.exe&quot; (
        ECHO &quot;START '' FileZilla Server Interface.exe&quot;
        START &quot;&quot; &quot;FileZilla Server Interface.exe&quot;
    )
    ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO FILEZILLAMENU
:startClientTools 
    ECHO. 
    ECHO.启动FileZilla FTP Client...... 
    IF NOT EXIST &quot;%FZ_CLIENT%filezilla.exe&quot; ECHO &quot;%FZ_CLIENT%filezilla.exe&quot;不存在 
    %FZ% 
    cd &quot;%FZ_CLIENT%&quot; 
    IF EXIST &quot;%FZ_CLIENT%filezilla.exe&quot; (
        ECHO &quot;START '' filezilla.exe&quot;
        START &quot;&quot; filezilla.exe
    )
    ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO FILEZILLAMENU
	
	
	
:9
@ECHO 进入Apple菜单选项
@ECHO off
TITLE  Apple 管理程序 %date% %time% 
:APPLEMENU 
CLS 
ECHO. 
ECHO. * * Apple 管理程序  *  
ECHO. * Apple 进程 List   *  
taskList|findstr /i /b &quot;Apple&quot;
taskList|findstr /i /b &quot;mDNSResponder.exe&quot;
ECHO. 
    ECHO.  [1] 启动Apple
    ECHO.  [2] 关闭Apple
    ECHO.  [3] 重启Apple
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET AppleSession=&quot;&quot;
SET /p AppleSession=Select[1/2/3/4]:
	IF /i &quot;%AppleSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%AppleSession%&quot;==&quot;1&quot; (goto:startApple) 
    IF /i &quot;%AppleSession%&quot;==&quot;2&quot; (goto:stopApple) 
    IF /i &quot;%AppleSession%&quot;==&quot;3&quot; (goto:restartApple) 
    IF /i &quot;%AppleSession%&quot;==&quot;4&quot; (goto:back)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:startApple 
    CALL :startAppleServer
    GOTO APPLEMENU
:stopApple  
    CALL :shutdownApple
    GOTO APPLEMENU
:restartApple 
    CALL :shutdownApple
    CALL :startAppleServer
    GOTO APPLEMENU
:shutdownApple
    @ECHO 正在停止苹果服务...
	NET STOP &quot;Apple Mobile Device&quot;
	NET STOP &quot;Bonjour Service&quot;
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startAppleServer
    @ECHO 正在启动苹果服务...
	NET START &quot;Apple Mobile Device&quot;
	NET START &quot;Bonjour Service&quot;
	ECHO 服务启动完毕!
	ping 127.0.0.1 /n 3
	GOTO APPLEMENU
	
	
	
:10
@ECHO 进入IPConfig菜单选项
@ECHO off
TITLE  IPConfig 管理程序 %date% %time% 
:IPCONFIGMENU 
CLS 
ECHO. 
ECHO. * * IPConfig 管理程序  *  
ECHO. 
    ECHO.  [1] 自动获取无线网IP
    ECHO.  [2] 设置指定无线IP
    ECHO.  [3] 自动获取本地IP
    ECHO.  [4] 设置指定本地IP
	ECHO.  [5] 隐藏本机
	ECHO.  [6] 显示本机
	ECHO.  [7] 移动内外网设置
ECHO. 
ECHO.请输入选择项目的序号:
SET IPConfigSession=&quot;&quot;
SET /p IPConfigSession=Select[1/2/3/4/5/6/7]:
	IF /i &quot;%IPConfigSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%IPConfigSession%&quot;==&quot;1&quot; (goto:autoGetWlanIp) 
    IF /i &quot;%IPConfigSession%&quot;==&quot;2&quot; (goto:setWlanIp) 
    IF /i &quot;%IPConfigSession%&quot;==&quot;3&quot; (goto:autoGetLanIp) 
    IF /i &quot;%IPConfigSession%&quot;==&quot;4&quot; (goto:setLanIp)
	IF /i &quot;%IPConfigSession%&quot;==&quot;5&quot; (goto:hideIp)
	IF /i &quot;%IPConfigSession%&quot;==&quot;6&quot; (goto:showIp)
	IF /i &quot;%IPConfigSession%&quot;==&quot;7&quot; (goto:jscmccSetWlan)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:autoGetWlanIp 
    netsh interface IP SET address &quot;无线网络连接&quot; source=dhcp
	netsh interface IP SET dns &quot;无线网络连接&quot; source=dhcp
    GOTO IPCONFIGMENU
:setWlanIp
	@ECHO 设置无线指定IP
	netsh interface IP SET address &quot;无线网络连接&quot; static 192.168.1.191 255.255.255.0 gateway=192.168.1.1 1
	netsh interface IP SET dns &quot;无线网络连接&quot; static addr=192.168.1.1
	netsh interface IP add dns &quot;无线网络连接&quot; addr=
	GOTO IPCONFIGMENU
:autoGetLanIp
	@ECHO 自动获取本地IP
	netsh interface IP SET address &quot;本地连接&quot; source=dhcp
	netsh interface IP SET dns &quot;本地连接&quot; source=dhcp
	GOTO IPCONFIGMENU
:setLanIp
	@ECHO 设置本地指定IP
	netsh interface IP SET address &quot;本地连接&quot; static 10.189.88.169 255.255.255.0 gateway=10.189.88.254
	netsh interface IP SET dns &quot;本地连接&quot; static addr=10.189.45.2
	netsh interface IP add dns &quot;本地连接&quot; addr=
    GOTO IPCONFIGMENU
:jscmccSetWlan
	@ECHO 移动内外网设置开始
	route delete 0.0.0.0
	route delete 10.0.0.0
	route add 0.0.0.0 mask 0.0.0.0 192.168.1.1
	route add 10.0.0.0 mask 255.0.0.0 10.32.156.193 
	@ECHO 移动内外网设置结束
	GOTO IPCONFIGMENU
:hideIp
	@ECHO 隐藏本机
	net config server /hidden:yes
	GOTO IPCONFIGMENU
:showIp
	@ECHO 显示本机
	net config server /hidden:no
	GOTO IPCONFIGMENU
	
:11
@ECHO 进入MongoDB Redis菜单选项
@ECHO off
TITLE  MongoDB Redis 管理程序 %date% %time% 
:MongoDBRedisMENU 
CLS 
ECHO. 
ECHO. * * MongoDB Redis 管理程序  *  
ECHO. 
    ECHO.  [1] 启动 MongoDB 服务
    ECHO.  [2] 关闭 MongoDB 服务
    ECHO.  [3] 启动 Redis 服务
	ECHO.  [5] 安装 MongoDB 服务
ECHO. 
ECHO.请输入选择项目的序号:
SET MongoDBRedisSession=&quot;&quot;
SET /p MongoDBRedisSession=Select[1/2/3/4/5]:
	IF /i &quot;%MongoDBRedisSession%&quot;==&quot;0&quot; (goto:back)
    IF /i &quot;%MongoDBRedisSession%&quot;==&quot;1&quot; (goto:MongoDBStart) 
    IF /i &quot;%MongoDBRedisSession%&quot;==&quot;2&quot; (goto:MongoDBStop) 
    IF /i &quot;%MongoDBRedisSession%&quot;==&quot;3&quot; (goto:RedisStart) 
    IF /i &quot;%MongoDBRedisSession%&quot;==&quot;4&quot; (goto:InstallMongoDBServices)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:MongoDBStart 
	@ECHO 启动MongoDB服务
	NET START MongoDB
	ping 127.0.0.1 /n 3
    GOTO MongoDBRedisMENU
:MongoDBStop
	@ECHO 关闭MongoDB服务
	NET STOP MongoDB
	ping 127.0.0.1 /n 3
	GOTO MongoDBRedisMENU
:RedisStart
	@ECHO 启动Redis服务
	cd &quot;/d D:\tools\redis&quot;
	start redis-server.exe redis.windows.conf
	ping 127.0.0.1 /n 3
	GOTO MongoDBRedisMENU
:InstallMongoDBServices
	@ECHO 安装MongoDB服务
	cd &quot;/d D:\tools\mongodb\bin&quot;
	start mongod --dbpath=D:\tools\mongodb\data  --logpath=D:\tools\mongodb\log\MongoDB.log --install --serviceName &quot;MongoDB&quot;
	ping 127.0.0.1 /n 3
	GOTO MongoDBRedisMENU</pre>
<br />
<br />

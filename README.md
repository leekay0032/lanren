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
SET session=""
SET /p session=Select[1/2/3/4/5/6/7/8/9/10/11]:
if /i "%session%"=="0" (goto:0)
if /i "%session%"=="1" (goto:1)
if /i "%session%"=="2" (goto:2)
if /i "%session%"=="3" (goto:3)
if /i "%session%"=="4" (goto:4)
if /i "%session%"=="5" (goto:5)
if /i "%session%"=="6" (goto:6)
if /i "%session%"=="9" (goto:9)
if /i "%session%"=="10" (goto:10)
if /i "%session%"=="11" (goto:11)

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
taskList|findstr /i /b "oracle"
taskList|findstr /i /b "tnslsnr"
ECHO. 
    ECHO.  [1] 启动Oracle
    ECHO.  [2] 关闭Oracle
    ECHO.  [3] 重启Oracle
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET OracleSession=""
SET /p OracleSession=Select[1/2/3/4]:
	IF /i "%OracleSession%"=="0" (goto:back)
    IF /i "%OracleSession%"=="1" (goto:startOracle) 
    IF /i "%OracleSession%"=="2" (goto:stopOracle) 
    IF /i "%OracleSession%"=="3" (goto:restartOracle) 
    IF /i "%OracleSession%"=="4" (goto:back)
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
    @ECHO "正在关闭Oracle相关开机服务..."
	NET STOP "OracleOraDb11g_home1TNSListener"
	NET STOP "OracleServiceORCL"
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startOracleServer
    @ECHO "正在启动Oracle相关开机服务..."
	NET START "OracleServiceORCL"
	NET START "OracleOraDb11g_home1TNSListener"
	@ECHO "服务启动完毕!"
	@ECHO "检测监听状态"
	lsnrctl status
	ping 127.0.0.1 /n 3
	@ECHO "检测服务状态"
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
taskList|findstr /i /b "sqlservr"
ECHO. 
    ECHO.  [1] 启动SqlServer
    ECHO.  [2] 关闭SqlServer
    ECHO.  [3] 重启SqlServer
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET SqlServerSession=""
SET /p SqlServerSession=Select[1/2/3/4]:
	IF /i "%SqlServerSession%"=="0" (goto:back)
    IF /i "%SqlServerSession%"=="1" (goto:startSqlServer) 
    IF /i "%SqlServerSession%"=="2" (goto:stopSqlServer) 
    IF /i "%SqlServerSession%"=="3" (goto:restartSqlServer) 
    IF /i "%SqlServerSession%"=="4" (goto:back)
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
    @ECHO "正在关闭SqlServer相关开机服务..."
	NET STOP "MSSQLSERVER"
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startSqlServers
    @ECHO "正在启动SqlServer相关开机服务..."
	NET START "MSSQLSERVER"
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
taskList|findstr /i /b "mysql"
ECHO. 
    ECHO.  [1] 启动MySQL
    ECHO.  [2] 关闭MySQL
    ECHO.  [3] 重启MySQL
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET MySQLSession=""
SET /p MySQLSession=Select[1/2/3/4]:
	IF /i "%MySQLSession%"=="0" (goto:back)
    IF /i "%MySQLSession%"=="1" (goto:startMySQL) 
    IF /i "%MySQLSession%"=="2" (goto:stopMySQL) 
    IF /i "%MySQLSession%"=="3" (goto:restartMySQL) 
    IF /i "%MySQLSession%"=="4" (goto:back)
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
    @ECHO "正在关闭MySQL相关开机服务..."
	NET STOP "MySQL"
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startMySQLServer
    @ECHO "正在启动MySQL相关开机服务..."
	NET START "MySQL"
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
taskList|findstr /i /b "vm"
ECHO. 
    ECHO.  [1] 启动VMware
    ECHO.  [2] 关闭VMware
    ECHO.  [3] 重启VMware
	ECHO.  [4] 启动VMware界面
    ECHO.  [5] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET VMwareSession=""
SET /p VMwareSession=Select[1/2/3/4/5]:
	IF /i "%VMwareSession%"=="0" (goto:back)
    IF /i "%VMwareSession%"=="1" (goto:startVMware) 
    IF /i "%VMwareSession%"=="2" (goto:stopVMware) 
    IF /i "%VMwareSession%"=="3" (goto:restartVMware) 
	IF /i "%VMwareSession%"=="4" (goto:startVMwareexe) 
    IF /i "%VMwareSession%"=="5" (goto:back)
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
    @ECHO "正在关闭VMware相关开机服务..."
	NET STOP "VMwareHostd"
	NET STOP "VMAuthdService"
	NET STOP "VMnetDHCP"
	NET STOP "VMware NAT Service"
	NET STOP "VMUSBArbService"
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startVMwareServer
    @ECHO "正在启动VMware相关开机服务..."
	NET START "VMwareHostd"
	NET START "VMAuthdService"
	NET START "VMnetDHCP"
	NET START "VMware NAT Service"
	NET START "VMUSBArbService"
	ECHO 服务启动完毕!
	ping 127.0.0.1 /n 3
	GOTO VMWAREMENU
:startVMwareexe
    ECHO. 
    ECHO.启动VMware...... 
    IF NOT EXIST "%VMWARE_DIR%vmware.exe" ECHO "%VMWARE_DIR%vmware.exe"不存在 
    %VMWARE_PATH% 
    cd "%VMWARE_DIR%" 
    IF EXIST "%VMWARE_DIR%vmware.exe" (
        ECHO "start '' vmware.exe"
        start "" vmware.exe
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
taskList|findstr /i "nginx.exe"
ECHO. 
    ECHO.  [1] 启动Nginx  
    ECHO.  [2] 关闭Nginx  
    ECHO.  [3] 重启Nginx  
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET NginxSession=""
SET /p NginxSession=Select[1/2/3/4]:
	IF /i "%NginxSession%"=="0" (goto:back)
    IF /i "%NginxSession%"=="1" (goto:startNginx) 
    IF /i "%NginxSession%"=="2" (goto:stopNginx) 
    IF /i "%NginxSession%"=="3" (goto:restartNginx) 
    IF /i "%NginxSession%"=="4" (goto:back)
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
    taskkill /F /IM nginx.exe > nul
    ECHO.OK,关闭所有nginx.exe 进程
    GOTO: EOF
:startNginxServer
    ECHO. 
    ECHO.启动NginxServer...... 
    IF NOT EXIST "%NGINX_DIR%nginx.exe" ECHO "%NGINX_DIR%nginx.exe"不存在 
    %NGINX_PATH% 
    cd "%NGINX_DIR%" 
    IF EXIST "%NGINX_DIR%nginx.exe" (
        ECHO "start '' nginx.exe"
        start "" nginx.exe
    )
    ECHO.OK
	GOTO NGINXMENU
	
	
:6
@ECHO 进入FileZilla菜单选项
@ECHO off
TITLE FileZilla 管理程序 %date% %time% 
CLS 
SET FZ=D:
SET FZ_SERVER="D:\Program Files (x86)\FileZilla Server"
SET FZ_CLIENT="D:\Program Files (x86)\FileZilla FTP Client"
:FILEZILLAMENU 
CLS 
ECHO. 
ECHO. * * FileZilla 管理程序  *  
ECHO. 
ECHO. * FileZilla 进程 List   *  
taskList|findstr /i /b "FileZilla Server.exe"
ECHO. 
    ECHO.  [1] 启动FileZilla  
    ECHO.  [2] 关闭FileZilla  
    ECHO.  [3] 重启FileZilla  
	ECHO.  [4] 启动FileZilla服务端接口 
	ECHO.  [5] 启动FileZilla客户端 
    ECHO.  [6] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET FileZillaSession=""
SET /p FileZillaSession=Select[1/2/3/4/5/6]:
	IF /i "%FileZillaSession%"=="0" (goto:back)
    IF /i "%FileZillaSession%"=="1" (goto:startServer) 
    IF /i "%FileZillaSession%"=="2" (goto:stopServer) 
    IF /i "%FileZillaSession%"=="3" (goto:restartServer) 
	IF /i "%FileZillaSession%"=="4" (goto:startServerInterface)
	IF /i "%FileZillaSession%"=="5" (goto:startClientTools)
    IF /i "%FileZillaSession%"=="6" (goto:back)
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
    NET STOP "FileZilla Server"
    ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startFileZillaServer
    ECHO. 
    ECHO.启动FileZilla Server...... 
    NET START "FileZilla Server"
	ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO FILEZILLAMENU
:startServerInterface 
    ECHO. 
    ECHO.启动FileZilla Server Interface...... 
    IF NOT EXIST %FZ_SERVER%"FileZilla Server Interface.exe" ECHO "%FZ_SERVER%FileZilla Server Interface.exe"不存在 
    %FZ% 
    cd "%FZ_SERVER%" 
    IF EXIST "%FZ_SERVER%FileZilla Server Interface.exe" (
        ECHO "START '' FileZilla Server Interface.exe"
        START "" "FileZilla Server Interface.exe"
    )
    ECHO.OK
	ping 127.0.0.1 /n 3
	GOTO FILEZILLAMENU
:startClientTools 
    ECHO. 
    ECHO.启动FileZilla FTP Client...... 
    IF NOT EXIST "%FZ_CLIENT%filezilla.exe" ECHO "%FZ_CLIENT%filezilla.exe"不存在 
    %FZ% 
    cd "%FZ_CLIENT%" 
    IF EXIST "%FZ_CLIENT%filezilla.exe" (
        ECHO "START '' filezilla.exe"
        START "" filezilla.exe
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
taskList|findstr /i /b "Apple"
taskList|findstr /i /b "mDNSResponder.exe"
ECHO. 
    ECHO.  [1] 启动Apple
    ECHO.  [2] 关闭Apple
    ECHO.  [3] 重启Apple
    ECHO.  [4] 返回上级 
ECHO. 
ECHO.请输入选择项目的序号:
SET AppleSession=""
SET /p AppleSession=Select[1/2/3/4]:
	IF /i "%AppleSession%"=="0" (goto:back)
    IF /i "%AppleSession%"=="1" (goto:startApple) 
    IF /i "%AppleSession%"=="2" (goto:stopApple) 
    IF /i "%AppleSession%"=="3" (goto:restartApple) 
    IF /i "%AppleSession%"=="4" (goto:back)
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
	NET STOP "Apple Mobile Device"
	NET STOP "Bonjour Service"
	ECHO 服务已关闭!
	ping 127.0.0.1 /n 3
	GOTO: EOF
:startAppleServer
    @ECHO 正在启动苹果服务...
	NET START "Apple Mobile Device"
	NET START "Bonjour Service"
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
SET IPConfigSession=""
SET /p IPConfigSession=Select[1/2/3/4/5/6/7]:
	IF /i "%IPConfigSession%"=="0" (goto:back)
    IF /i "%IPConfigSession%"=="1" (goto:autoGetWlanIp) 
    IF /i "%IPConfigSession%"=="2" (goto:setWlanIp) 
    IF /i "%IPConfigSession%"=="3" (goto:autoGetLanIp) 
    IF /i "%IPConfigSession%"=="4" (goto:setLanIp)
	IF /i "%IPConfigSession%"=="5" (goto:hideIp)
	IF /i "%IPConfigSession%"=="6" (goto:showIp)
	IF /i "%IPConfigSession%"=="7" (goto:jscmccSetWlan)
:back 
    goto:A
	ping 127.0.0.1 /n 3
:autoGetWlanIp 
    netsh interface IP SET address "无线网络连接" source=dhcp
	netsh interface IP SET dns "无线网络连接" source=dhcp
    GOTO IPCONFIGMENU
:setWlanIp
	@ECHO 设置无线指定IP
	netsh interface IP SET address "无线网络连接" static 192.168.1.191 255.255.255.0 gateway=192.168.1.1 1
	netsh interface IP SET dns "无线网络连接" static addr=192.168.1.1
	netsh interface IP add dns "无线网络连接" addr=
	GOTO IPCONFIGMENU
:autoGetLanIp
	@ECHO 自动获取本地IP
	netsh interface IP SET address "本地连接" source=dhcp
	netsh interface IP SET dns "本地连接" source=dhcp
	GOTO IPCONFIGMENU
:setLanIp
	@ECHO 设置本地指定IP
	netsh interface IP SET address "本地连接" static 10.189.88.169 255.255.255.0 gateway=10.189.88.254
	netsh interface IP SET dns "本地连接" static addr=10.189.45.2
	netsh interface IP add dns "本地连接" addr=
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
SET MongoDBRedisSession=""
SET /p MongoDBRedisSession=Select[1/2/3/4/5]:
	IF /i "%MongoDBRedisSession%"=="0" (goto:back)
    IF /i "%MongoDBRedisSession%"=="1" (goto:MongoDBStart) 
    IF /i "%MongoDBRedisSession%"=="2" (goto:MongoDBStop) 
    IF /i "%MongoDBRedisSession%"=="3" (goto:RedisStart) 
    IF /i "%MongoDBRedisSession%"=="4" (goto:InstallMongoDBServices)
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
	cd "/d D:\tools\redis"
	start redis-server.exe redis.windows.conf
	ping 127.0.0.1 /n 3
	GOTO MongoDBRedisMENU
:InstallMongoDBServices
	@ECHO 安装MongoDB服务
	cd "/d D:\tools\mongodb\bin"
	start mongod --dbpath=D:\tools\mongodb\data  --logpath=D:\tools\mongodb\log\MongoDB.log --install --serviceName "MongoDB"
	ping 127.0.0.1 /n 3
	GOTO MongoDBRedisMENU

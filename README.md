<p>
    @ECHO off
</p>
<p>
    TITLE Switch %date% %time% &nbsp;欢迎使用
</p>
<p>
    :A
</p>
<p>
    color A
</p>
<p>
    CLS
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;++++++++++++++++++++++++++++++++++++++++++++++++
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;WELCOME &nbsp;TO &nbsp;MY &nbsp;SCRIPT ! &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; =
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;启动Oracle服务菜单 = 1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;启动SqlServer服务菜单= 2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;启动MySql服务菜单 = 3 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; =
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;启动虚拟机服务菜单 = 4 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;进入Nginx菜单选项 = 5 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; =
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;进入FileZilla菜单选项 = 6 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; =
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;开启苹果服务单选项 = 9 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;进入IpConfig服务菜单 = 10 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; =
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= &nbsp;进入MongoDB Redis服务菜单 = 11 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=
</p>
<p>
    ECHO &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;++++++++++++++++++++++++++++++++++++++++++++++++
</p>
<p>
    ECHO.
</p>
<p>
    ECHO.
</p>
<p>
    SET session=&quot;&quot;
</p>
<p>
    SET /p session=Select[1/2/3/4/5/6/7/8/9/10/11]:
</p>
<p>
    if /i &quot;%session%&quot;==&quot;0&quot; (goto:0)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;1&quot; (goto:1)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;2&quot; (goto:2)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;3&quot; (goto:3)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;4&quot; (goto:4)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;5&quot; (goto:5)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;6&quot; (goto:6)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;9&quot; (goto:9)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;10&quot; (goto:10)
</p>
<p>
    if /i &quot;%session%&quot;==&quot;11&quot; (goto:11)
</p>
<p>
    <br/>
</p>
<p>
    :0
</p>
<p>
    CLS
</p>
<p>
    @ECHO 谢谢使用...
</p>
<p>
    ping 127.0.0.1 /n 3
</p>
<p>
    exit
</p>
<p>
    <br/>
</p>
<p>
    <br/>
</p>
<p>
    <br/>
</p>
<p>
    :1
</p>
<p>
    @ECHO 进入Oracle菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;Oracle 管理程序 %date% %time%&nbsp;
</p>
<p>
    :ORACLEMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * Oracle 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO. * Oracle 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;oracle&quot;
</p>
<p>
    taskList|findstr /i /b &quot;tnslsnr&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动Oracle
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭Oracle
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启Oracle
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET OracleSession=&quot;&quot;
</p>
<p>
    SET /p OracleSession=Select[1/2/3/4]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%OracleSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%OracleSession%&quot;==&quot;1&quot; (goto:startOracle)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%OracleSession%&quot;==&quot;2&quot; (goto:stopOracle)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%OracleSession%&quot;==&quot;3&quot; (goto:restartOracle)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%OracleSession%&quot;==&quot;4&quot; (goto:back)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; GOTO:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startOracle&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startOracleServer
</p>
<p>
    &nbsp; &nbsp; GOTO ORACLEMENU
</p>
<p>
    :stopOracle&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownOracle
</p>
<p>
    &nbsp; &nbsp; GOTO ORACLEMENU
</p>
<p>
    :restartOracle&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownOracle
</p>
<p>
    &nbsp; &nbsp; CALL :startOracleServer
</p>
<p>
    &nbsp; &nbsp; GOTO ORACLEMENU
</p>
<p>
    :shutdownOracle
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在关闭Oracle相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;OracleOraDb11g_home1TNSListener&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;OracleServiceORCL&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务已关闭!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startOracleServer
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在启动Oracle相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;OracleServiceORCL&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;OracleOraDb11g_home1TNSListener&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO &quot;服务启动完毕!&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO &quot;检测监听状态&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>lsnrctl status
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO &quot;检测服务状态&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>tnsping orcl
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO ORACLEMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <br/>
</p>
<p>
    :2
</p>
<p>
    @ECHO 进入SqlServer菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;SqlServer 管理程序 %date% %time%&nbsp;
</p>
<p>
    :SQLSERVERMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * SqlServer 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO. * SqlServer 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;sqlservr&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动SqlServer
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭SqlServer
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启SqlServer
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET SqlServerSession=&quot;&quot;
</p>
<p>
    SET /p SqlServerSession=Select[1/2/3/4]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%SqlServerSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%SqlServerSession%&quot;==&quot;1&quot; (goto:startSqlServer)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%SqlServerSession%&quot;==&quot;2&quot; (goto:stopSqlServer)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%SqlServerSession%&quot;==&quot;3&quot; (goto:restartSqlServer)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%SqlServerSession%&quot;==&quot;4&quot; (goto:back)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startSqlServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startSqlServers
</p>
<p>
    &nbsp; &nbsp; GOTO SQLSERVERMENU
</p>
<p>
    :stopSqlServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownSqlServer
</p>
<p>
    &nbsp; &nbsp; GOTO SQLSERVERMENU
</p>
<p>
    :restartSqlServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownSqlServer
</p>
<p>
    &nbsp; &nbsp; CALL :startSqlServers
</p>
<p>
    &nbsp; &nbsp; GOTO SQLSERVERMENU
</p>
<p>
    :shutdownSqlServer
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在关闭SqlServer相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;MSSQLSERVER&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务已关闭!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startSqlServers
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在启动SqlServer相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;MSSQLSERVER&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务启动完毕!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO SQLSERVERMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :3
</p>
<p>
    @ECHO 进入MySQL菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;MySQL 管理程序 %date% %time%&nbsp;
</p>
<p>
    :MYSQLMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * MySQL 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO. * MySQL 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;mysql&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动MySQL
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭MySQL
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启MySQL
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET MySQLSession=&quot;&quot;
</p>
<p>
    SET /p MySQLSession=Select[1/2/3/4]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%MySQLSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MySQLSession%&quot;==&quot;1&quot; (goto:startMySQL)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MySQLSession%&quot;==&quot;2&quot; (goto:stopMySQL)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MySQLSession%&quot;==&quot;3&quot; (goto:restartMySQL)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MySQLSession%&quot;==&quot;4&quot; (goto:back)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startMySQL&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startMySQLServer
</p>
<p>
    &nbsp; &nbsp; GOTO MYSQLMENU
</p>
<p>
    :stopMySQL&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownMySQL
</p>
<p>
    &nbsp; &nbsp; GOTO MYSQLMENU
</p>
<p>
    :restartMySQL&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownMySQL
</p>
<p>
    &nbsp; &nbsp; CALL :startMySQLServer
</p>
<p>
    &nbsp; &nbsp; GOTO MYSQLMENU
</p>
<p>
    :shutdownMySQL
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在关闭MySQL相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;MySQL&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务已关闭!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startMySQLServer
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在启动MySQL相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;MySQL&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务启动完毕!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO MYSQLMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <br/>
</p>
<p>
    :4
</p>
<p>
    @ECHO 进入VMware菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;VMware 管理程序 %date% %time%&nbsp;
</p>
<p>
    SET VMWARE_PATH=D:
</p>
<p>
    SET VMWARE_DIR=D:\Program Files\VMware\
</p>
<p>
    :VMWAREMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * VMware 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * VMware 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;vm&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动VMware
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭VMware
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启VMware
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[4] 启动VMware界面
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[5] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET VMwareSession=&quot;&quot;
</p>
<p>
    SET /p VMwareSession=Select[1/2/3/4/5]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%VMwareSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%VMwareSession%&quot;==&quot;1&quot; (goto:startVMware)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%VMwareSession%&quot;==&quot;2&quot; (goto:stopVMware)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%VMwareSession%&quot;==&quot;3&quot; (goto:restartVMware)&nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%VMwareSession%&quot;==&quot;4&quot; (goto:startVMwareexe)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%VMwareSession%&quot;==&quot;5&quot; (goto:back)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startVMware&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startVMwareServer
</p>
<p>
    &nbsp; &nbsp; GOTO VMWAREMENU
</p>
<p>
    :stopVMware&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownVMware
</p>
<p>
    &nbsp; &nbsp; GOTO VMWAREMENU
</p>
<p>
    :restartVMware&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownVMware
</p>
<p>
    &nbsp; &nbsp; CALL :startVMwareServer
</p>
<p>
    &nbsp; &nbsp; GOTO VMWAREMENU
</p>
<p>
    :shutdownVMware
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在关闭VMware相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;VMwareHostd&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;VMAuthdService&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;VMnetDHCP&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;VMware NAT Service&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;VMUSBArbService&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务已关闭!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startVMwareServer
</p>
<p>
    &nbsp; &nbsp; @ECHO &quot;正在启动VMware相关开机服务...&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;VMwareHostd&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;VMAuthdService&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;VMnetDHCP&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;VMware NAT Service&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;VMUSBArbService&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务启动完毕!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO VMWAREMENU
</p>
<p>
    :startVMwareexe
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.启动VMware......&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF NOT EXIST &quot;%VMWARE_DIR%vmware.exe&quot; ECHO &quot;%VMWARE_DIR%vmware.exe&quot;不存在&nbsp;
</p>
<p>
    &nbsp; &nbsp; %VMWARE_PATH%&nbsp;
</p>
<p>
    &nbsp; &nbsp; cd &quot;%VMWARE_DIR%&quot;&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF EXIST &quot;%VMWARE_DIR%vmware.exe&quot; (
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; ECHO &quot;start &#39;&#39; vmware.exe&quot;
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; start &quot;&quot; vmware.exe
</p>
<p>
    &nbsp; &nbsp; )
</p>
<p>
    &nbsp; &nbsp; ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO VMWAREMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :5
</p>
<p>
    @ECHO 进入Nginx菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE Nginx 管理程序 %date% %time%&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    SET NGINX_PATH=D:
</p>
<p>
    SET NGINX_DIR=D:\tools\nginx\
</p>
<p>
    :NGINXMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * Nginx 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * Nginx 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i &quot;nginx.exe&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动Nginx &nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭Nginx &nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启Nginx &nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET NginxSession=&quot;&quot;
</p>
<p>
    SET /p NginxSession=Select[1/2/3/4]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%NginxSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%NginxSession%&quot;==&quot;1&quot; (goto:startNginx)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%NginxSession%&quot;==&quot;2&quot; (goto:stopNginx)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%NginxSession%&quot;==&quot;3&quot; (goto:restartNginx)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%NginxSession%&quot;==&quot;4&quot; (goto:back)
</p>
<p>
    :back
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>CLS
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startNginx&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startNginxServer
</p>
<p>
    &nbsp; &nbsp; GOTO NGINXMENU
</p>
<p>
    :stopNginx&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownNginx
</p>
<p>
    &nbsp; &nbsp; GOTO NGINXMENU
</p>
<p>
    :restartNginx&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownNginx
</p>
<p>
    &nbsp; &nbsp; CALL :startNginxServer
</p>
<p>
    &nbsp; &nbsp; GOTO NGINXMENU
</p>
<p>
    :shutdownNginx
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.关闭NginxServer......&nbsp;
</p>
<p>
    &nbsp; &nbsp; taskkill /F /IM nginx.exe &gt; nul
</p>
<p>
    &nbsp; &nbsp; ECHO.OK,关闭所有nginx.exe 进程
</p>
<p>
    &nbsp; &nbsp; GOTO: EOF
</p>
<p>
    :startNginxServer
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.启动NginxServer......&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF NOT EXIST &quot;%NGINX_DIR%nginx.exe&quot; ECHO &quot;%NGINX_DIR%nginx.exe&quot;不存在&nbsp;
</p>
<p>
    &nbsp; &nbsp; %NGINX_PATH%&nbsp;
</p>
<p>
    &nbsp; &nbsp; cd &quot;%NGINX_DIR%&quot;&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF EXIST &quot;%NGINX_DIR%nginx.exe&quot; (
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; ECHO &quot;start &#39;&#39; nginx.exe&quot;
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; start &quot;&quot; nginx.exe
</p>
<p>
    &nbsp; &nbsp; )
</p>
<p>
    &nbsp; &nbsp; ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO NGINXMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :6
</p>
<p>
    @ECHO 进入FileZilla菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE FileZilla 管理程序 %date% %time%&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    SET FZ=D:
</p>
<p>
    SET FZ_SERVER=&quot;D:\Program Files (x86)\FileZilla Server&quot;
</p>
<p>
    SET FZ_CLIENT=&quot;D:\Program Files (x86)\FileZilla FTP Client&quot;
</p>
<p>
    :FILEZILLAMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * FileZilla 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * FileZilla 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;FileZilla Server.exe&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动FileZilla &nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭FileZilla &nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启FileZilla &nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[4] 启动FileZilla服务端接口&nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[5] 启动FileZilla客户端&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[6] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET FileZillaSession=&quot;&quot;
</p>
<p>
    SET /p FileZillaSession=Select[1/2/3/4/5/6]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%FileZillaSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%FileZillaSession%&quot;==&quot;1&quot; (goto:startServer)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%FileZillaSession%&quot;==&quot;2&quot; (goto:stopServer)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%FileZillaSession%&quot;==&quot;3&quot; (goto:restartServer)&nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%FileZillaSession%&quot;==&quot;4&quot; (goto:startServerInterface)
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%FileZillaSession%&quot;==&quot;5&quot; (goto:startClientTools)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%FileZillaSession%&quot;==&quot;6&quot; (goto:back)
</p>
<p>
    :back
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>CLS
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startFileZillaServer
</p>
<p>
    &nbsp; &nbsp; GOTO FILEZILLAMENU
</p>
<p>
    :stopServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownFileZillaServer
</p>
<p>
    &nbsp; &nbsp; GOTO FILEZILLAMENU
</p>
<p>
    :restartServer&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownFileZillaServer
</p>
<p>
    &nbsp; &nbsp; CALL :startFileZillaServer
</p>
<p>
    &nbsp; &nbsp; GOTO FILEZILLAMENU
</p>
<p>
    :shutdownFileZillaServer
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.关闭FileZilla......&nbsp;
</p>
<p>
    &nbsp; &nbsp; NET STOP &quot;FileZilla Server&quot;
</p>
<p>
    &nbsp; &nbsp; ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startFileZillaServer
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.启动FileZilla Server......&nbsp;
</p>
<p>
    &nbsp; &nbsp; NET START &quot;FileZilla Server&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO FILEZILLAMENU
</p>
<p>
    :startServerInterface&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.启动FileZilla Server Interface......&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF NOT EXIST %FZ_SERVER%&quot;FileZilla Server Interface.exe&quot; ECHO &quot;%FZ_SERVER%FileZilla Server Interface.exe&quot;不存在&nbsp;
</p>
<p>
    &nbsp; &nbsp; %FZ%&nbsp;
</p>
<p>
    &nbsp; &nbsp; cd &quot;%FZ_SERVER%&quot;&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF EXIST &quot;%FZ_SERVER%FileZilla Server Interface.exe&quot; (
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; ECHO &quot;START &#39;&#39; FileZilla Server Interface.exe&quot;
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; START &quot;&quot; &quot;FileZilla Server Interface.exe&quot;
</p>
<p>
    &nbsp; &nbsp; )
</p>
<p>
    &nbsp; &nbsp; ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO FILEZILLAMENU
</p>
<p>
    :startClientTools&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO.启动FileZilla FTP Client......&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF NOT EXIST &quot;%FZ_CLIENT%filezilla.exe&quot; ECHO &quot;%FZ_CLIENT%filezilla.exe&quot;不存在&nbsp;
</p>
<p>
    &nbsp; &nbsp; %FZ%&nbsp;
</p>
<p>
    &nbsp; &nbsp; cd &quot;%FZ_CLIENT%&quot;&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF EXIST &quot;%FZ_CLIENT%filezilla.exe&quot; (
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; ECHO &quot;START &#39;&#39; filezilla.exe&quot;
</p>
<p>
    &nbsp; &nbsp; &nbsp; &nbsp; START &quot;&quot; filezilla.exe
</p>
<p>
    &nbsp; &nbsp; )
</p>
<p>
    &nbsp; &nbsp; ECHO.OK
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO FILEZILLAMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :9
</p>
<p>
    @ECHO 进入Apple菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;Apple 管理程序 %date% %time%&nbsp;
</p>
<p>
    :APPLEMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * Apple 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO. * Apple 进程 List &nbsp; * &nbsp;
</p>
<p>
    taskList|findstr /i /b &quot;Apple&quot;
</p>
<p>
    taskList|findstr /i /b &quot;mDNSResponder.exe&quot;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动Apple
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭Apple
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 重启Apple
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 返回上级&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET AppleSession=&quot;&quot;
</p>
<p>
    SET /p AppleSession=Select[1/2/3/4]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%AppleSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%AppleSession%&quot;==&quot;1&quot; (goto:startApple)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%AppleSession%&quot;==&quot;2&quot; (goto:stopApple)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%AppleSession%&quot;==&quot;3&quot; (goto:restartApple)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%AppleSession%&quot;==&quot;4&quot; (goto:back)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :startApple&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :startAppleServer
</p>
<p>
    &nbsp; &nbsp; GOTO APPLEMENU
</p>
<p>
    :stopApple &nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownApple
</p>
<p>
    &nbsp; &nbsp; GOTO APPLEMENU
</p>
<p>
    :restartApple&nbsp;
</p>
<p>
    &nbsp; &nbsp; CALL :shutdownApple
</p>
<p>
    &nbsp; &nbsp; CALL :startAppleServer
</p>
<p>
    &nbsp; &nbsp; GOTO APPLEMENU
</p>
<p>
    :shutdownApple
</p>
<p>
    &nbsp; &nbsp; @ECHO 正在停止苹果服务...
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;Apple Mobile Device&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP &quot;Bonjour Service&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务已关闭!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO: EOF
</p>
<p>
    :startAppleServer
</p>
<p>
    &nbsp; &nbsp; @ECHO 正在启动苹果服务...
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;Apple Mobile Device&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START &quot;Bonjour Service&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO 服务启动完毕!
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO APPLEMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :10
</p>
<p>
    @ECHO 进入IPConfig菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;IPConfig 管理程序 %date% %time%&nbsp;
</p>
<p>
    :IPCONFIGMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * IPConfig 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 自动获取无线网IP
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 设置指定无线IP
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 自动获取本地IP
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[4] 设置指定本地IP
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[5] 隐藏本机
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[6] 显示本机
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[7] 移动内外网设置
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET IPConfigSession=&quot;&quot;
</p>
<p>
    SET /p IPConfigSession=Select[1/2/3/4/5/6/7]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%IPConfigSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%IPConfigSession%&quot;==&quot;1&quot; (goto:autoGetWlanIp)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%IPConfigSession%&quot;==&quot;2&quot; (goto:setWlanIp)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%IPConfigSession%&quot;==&quot;3&quot; (goto:autoGetLanIp)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%IPConfigSession%&quot;==&quot;4&quot; (goto:setLanIp)
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%IPConfigSession%&quot;==&quot;5&quot; (goto:hideIp)
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%IPConfigSession%&quot;==&quot;6&quot; (goto:showIp)
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%IPConfigSession%&quot;==&quot;7&quot; (goto:jscmccSetWlan)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :autoGetWlanIp&nbsp;
</p>
<p>
    &nbsp; &nbsp; netsh interface IP SET address &quot;无线网络连接&quot; source=dhcp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET dns &quot;无线网络连接&quot; source=dhcp
</p>
<p>
    &nbsp; &nbsp; GOTO IPCONFIGMENU
</p>
<p>
    :setWlanIp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 设置无线指定IP
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET address &quot;无线网络连接&quot; static 192.168.1.191 255.255.255.0 gateway=192.168.1.1 1
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET dns &quot;无线网络连接&quot; static addr=192.168.1.1
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP add dns &quot;无线网络连接&quot; addr=
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO IPCONFIGMENU
</p>
<p>
    :autoGetLanIp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 自动获取本地IP
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET address &quot;本地连接&quot; source=dhcp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET dns &quot;本地连接&quot; source=dhcp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO IPCONFIGMENU
</p>
<p>
    :setLanIp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 设置本地指定IP
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET address &quot;本地连接&quot; static 10.189.88.169 255.255.255.0 gateway=10.189.88.254
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP SET dns &quot;本地连接&quot; static addr=10.189.45.2
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>netsh interface IP add dns &quot;本地连接&quot; addr=
</p>
<p>
    &nbsp; &nbsp; GOTO IPCONFIGMENU
</p>
<p>
    :jscmccSetWlan
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 移动内外网设置开始
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>route delete 0.0.0.0
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>route delete 10.0.0.0
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>route add 0.0.0.0 mask 0.0.0.0 192.168.1.1
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>route add 10.0.0.0 mask 255.0.0.0 10.32.156.193&nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 移动内外网设置结束
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO IPCONFIGMENU
</p>
<p>
    :hideIp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 隐藏本机
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>net config server /hidden:yes
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO IPCONFIGMENU
</p>
<p>
    :showIp
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 显示本机
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>net config server /hidden:no
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO IPCONFIGMENU
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>
</p>
<p>
    :11
</p>
<p>
    @ECHO 进入MongoDB Redis菜单选项
</p>
<p>
    @ECHO off
</p>
<p>
    TITLE &nbsp;MongoDB Redis 管理程序 %date% %time%&nbsp;
</p>
<p>
    :MongoDBRedisMENU&nbsp;
</p>
<p>
    CLS&nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO. * * MongoDB Redis 管理程序 &nbsp;* &nbsp;
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[1] 启动 MongoDB 服务
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[2] 关闭 MongoDB 服务
</p>
<p>
    &nbsp; &nbsp; ECHO. &nbsp;[3] 启动 Redis 服务
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ECHO. &nbsp;[5] 安装 MongoDB 服务
</p>
<p>
    ECHO.&nbsp;
</p>
<p>
    ECHO.请输入选择项目的序号:
</p>
<p>
    SET MongoDBRedisSession=&quot;&quot;
</p>
<p>
    SET /p MongoDBRedisSession=Select[1/2/3/4/5]:
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>IF /i &quot;%MongoDBRedisSession%&quot;==&quot;0&quot; (goto:back)
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MongoDBRedisSession%&quot;==&quot;1&quot; (goto:MongoDBStart)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MongoDBRedisSession%&quot;==&quot;2&quot; (goto:MongoDBStop)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MongoDBRedisSession%&quot;==&quot;3&quot; (goto:RedisStart)&nbsp;
</p>
<p>
    &nbsp; &nbsp; IF /i &quot;%MongoDBRedisSession%&quot;==&quot;4&quot; (goto:InstallMongoDBServices)
</p>
<p>
    :back&nbsp;
</p>
<p>
    &nbsp; &nbsp; goto:A
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    :MongoDBStart&nbsp;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 启动MongoDB服务
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET START MongoDB
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    &nbsp; &nbsp; GOTO MongoDBRedisMENU
</p>
<p>
    :MongoDBStop
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 关闭MongoDB服务
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>NET STOP MongoDB
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO MongoDBRedisMENU
</p>
<p>
    :RedisStart
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 启动Redis服务
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>cd &quot;/d D:\tools\redis&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>start redis-server.exe redis.windows.conf
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>GOTO MongoDBRedisMENU
</p>
<p>
    :InstallMongoDBServices
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>@ECHO 安装MongoDB服务
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>cd &quot;/d D:\tools\mongodb\bin&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>start mongod --dbpath=D:\tools\mongodb\data &nbsp;--logpath=D:\tools\mongodb\log\MongoDB.log --install --serviceName &quot;MongoDB&quot;
</p>
<p>
    <span class="Apple-tab-span" style="white-space:pre">	</span>ping 127.0.0.1 /n 3
</p>
<p>
    <span class="Apple-tab-span" style="white-space: pre;">	</span>GOTO MongoDBRedisMENU
</p>
<p>
    <br/>
</p>

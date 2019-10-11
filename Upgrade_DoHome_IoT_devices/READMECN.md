<a href="https://github.com/SmartArduino/DoHome/blob/master/Upgrade_DoHome_IoT_devices/README.md">English</a> | 中文版
<h2><span style="font-family: 宋体, SimSun; font-size: 16px">注意事项</span></h2><p style="font-family: arial, helvetica, sans-serif; font-size: 14px;">升级前请先联系：song@doit.am，确认是否可以升级。</p><p style="font-family: arial, helvetica, sans-serif; font-size: 14px;">固件（包含bootloader）大小不超过512KB</p><p style="font-family: arial, helvetica, sans-serif; font-size: 14px;">仅支持arduino开发的固件、esp-open-sdk、乐鑫nonos-SDK、以及非IDF框架RTOS SDK开发的固件。升级前请务必先联系上述邮件确认</p><h2><span style="font-family: 宋体, SimSun; font-size: 16px">1、所需软硬件</span></h2><h3><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">1.1 软件</span></h3><p><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">下载升级工具：</span></p><p><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="font-family: 宋体;">链接</span>：<br/><span style="font-size: 14px; font-family: arial, helvetica, sans-serif; color: red;"><a href="http://support.doiting.com/DoHome.zip">http://support.doiting.com/DoHome.zip</a></span></span></p><p><span style="font-family: arial, helvetica, sans-serif; font-size:14px;"><span style="font-family: 宋体; color: red; font-size: 14px;">如果你的电脑是32位系统则下载DoHome_JRE_32.zip；64位系统则下载DoHome_JRE_64.zip</span></span></p><p><span style="text-indent: 37px; font-family: arial, helvetica, sans-serif; font-size: 14px;">下载固件：</span></p><p><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="font-family: 宋体; font-size: 14px;">与升级工具同一下载地址。</span></span></p><p><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">如果被升级固件是esp-open-rtos开发的，可以直接升级&nbsp;</span></p><h3 style="margin-left: 0px; text-indent: 0px; margin-top: 5px; line-height: normal;"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">1.2 硬件</span></h3><p style="text-indent: 37px; margin-top: 5px; line-height: normal;"><span style="font-family: 宋体; font-size: 14px;">准备一台具有无线网卡的电脑</span></p><p style="text-indent: 37px; margin-top: 5px; line-height: normal;"><span style="font-family: 宋体; font-size: 14px;"><br/></span></p><h2 style="margin-left: 0px; text-indent: 0px;"><span style="font-size: 18px; font-family: arial, helvetica, sans-serif;">2<span style="font-size: 18px;">、升级步骤</span></span></h2><h3 style="margin-left: 0px; text-indent: 0px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">2.1 确认当前固件运行在第一个App区域</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">电脑连接被升级设备的热点（如果是DoHome系列固件，则热点名类似DoHome_xxxx）。连上该热点后打开电脑升级工具进入Third-party upgrade界面，如下图：</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567130888487228.png" title="1567130888487228.png" alt="EV$L86[$]M1O~Z77MTQCEB5.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图1</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">点击“Slot check”按钮，下方信息框会显示“Slot=1”或者“Slot=2”，如下图：</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131227436661.png" title="1567131227436661.png" alt=")MS5YSIGZMXME{N}3@H$_YW.png"/></p><p style="text-align: center;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图2 App区域检查</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Esp8285模组有两个固件运行区域，Slot=1表示当前固件运行在区域1；slot=2则是区域2。要升级到第三方固件时，升级前的固件必须运行在区域1。即<span style="font-family: arial, helvetica, sans-serif; color: red;">返回的内容必须是slot=1，如果是，则进行步骤2.2；如果不是，按照3.5节内容处理，然后再进行下面步骤2.2。</span>（大部分情况下固件都会是slot=1，不需要进行步骤3.4，除非之前有升级过固件）</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">2.2 升级到临时固件</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">临时固件位于prepare目录下，分别是u1.bin和u2.bin。</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">将你要升级的设备配置连接上路由器。电脑也连接同一路由器。打开电脑上的升级工具DoHome_v21.exe进入DoHome upgrade界面，填入临时固件u1.bin和u2.bin（即prepare目录下的两个文件）的路径，以及你的设备的IP。如下图</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131456410766.png" title="1567131456410766.png" alt="REL)FR61~4[P(65L`J_C5CV.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图3 固件升级界面</span></p><p style="text-indent: 37px; text-align: left;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">其他区域不用填写。点击Start upgrading即可开始升级。</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">2.3 设置临时固件连接路由器</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">设备升级到临时固件后，临时固件运行时会产生类似“Upgrade-xxxxxx”的热点。用手机连上该热点会自动弹出路由器设置界面，如下图：</span></p><p style="text-align:center"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131628605874.png" title="1567131628605874.png" alt="NY%B1SV[VH36W06FD}[YWN7.png"/><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131635765508.png" title="1567131635765508.png" alt="}D(NUBJ45GLOYIDEJ$X@F]6.png"/></p><p style="text-align:center"><span style="font-size: 14px; font-family: arial, helvetica, sans-serif;">图4 连接临时固件热点</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">点击你的路由器然后在下面的密码输入框输入你的路由器密码，点“Join”按钮后临时固件会自动连上你的路由器。</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">2.4 升级到第三方固件</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">确保你的电脑连接到步骤2.2中所设置的路由器。打开PC端升级软件，点击菜单栏下方的tab栏，选择“Third-party upgrade”。如下图：</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131715928253.png" title="1567131715928253.png" alt="EV$L86[$]M1O~Z77MTQCEB5.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图5 第三方固件升级</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">点击“Scan device”按钮，下方信息框会列出在该路由器下的已经升级到临时固件的设备信息。</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131915732446.png" title="1567131915732446.png" alt="E@EE4G$2P9E]{0$K)FG~W9Y.png"/><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131942214520.png" title="1567131942214520.png" alt="3RW{DKBRM22OMTG4BN1TWH5.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图6 扫描信息</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Dev_id字段是步骤2.2中临时固件热点名字，滑动条往下拉可以看到设备的IP地址。然后在Device IP一栏中填写列出的设备IP地址。在Firmware path一栏选择第三方固件的路径。如图7所示：</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567131978516677.png" title="1567131978516677.png" alt="3`2VSFYEK83)@{MUE~P7%OG.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图7 第三方固件设置</span></p><p style="text-indent: 37px; text-align: left;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">最后点击“Start upgrade”按钮即可开始升级第三方固件。</span></p><h2 style="margin-left: 0px; text-indent: 0px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 18px;">3、常见问题以及注意事项</span></h2><h3 style="margin-left: 0px; text-indent: 0px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.1 升级第三方固件时弹出提示“Current slot must be 1, when upgrade third-party firmware”</span></h3><p style="text-align:center"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567132182675035.png" title="1567132182675035.png" alt="T8OE3LHP]O9LI[YF@MO7S4B.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图8</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">这说明你的设备升级到临时固件前运行的固件不是在第一个app区域。检查你的操作过程是否有执行步骤2.1。</span></p><h3 style="margin-left: 0px; text-indent: 0px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.2 点“Scan device”按钮后没有列出设备IP</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">检查运行升级工具的电脑是否连接上步骤2.2中指定的路由器。电脑连接的路由器必须和2.2中指定的路由器一致。</span></p><h3 style="margin-left: 0px; text-indent: 0px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.3 第三方固件要求</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">升级的第三方固件要求必须包含有bootloader。可以使用乐鑫提供的将bootloader和用户程序打包成一个bin文件，如下图：</span></p><p style="text-align:center"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567132485797059.png" title="1567132485797059.png" alt="PR])%UT@QQ(3[P`5_Y~XT`4.png"/></p><p style="text-align:center"><span style="font-size:16px;font-family:宋体">图9</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.4 u1.bin与u2.bin路径</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">请注意不要将u1.bin和u2.bin的路径写反或填错，否则升级后可能造成设备无法再运行使用。</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-size: 16px font-family: arial, helvetica, sans-serif;">3.5 <span style="font-size: 16px">固件区域切换</span></span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">执行区域切换操作需要用到Dohome区域切换固件，该固件位于下载连接中“Dohome区域切换固件”目录下。包含u1.bin和u2.bin两个文件。</span></p><p style="text-align:center"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567132301526847.png" title="1567132301526847.png" alt="60JFU55[ZR_9C_7@D{A~{B0.png"/></p><p style="text-align:center"><span style="font-size:16px;font-family:宋体">图10</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">将设备配置连接上路由器后，打开升级软件，在“DoHome Upgrade”界面中填u1.bin和u2.bin的路径；在“Device IP”一栏填设备IP地址。如上图。为了获取设备IP，可以在“Third-party Upgrade”界面点击“Scan Device”按钮。下方消息栏会列出扫描到的设备IP（电脑需要连接设备所连接的路由器）。如下图：</span></p><p style="text-align: center;"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1567132362242981.png" title="1567132362242981.png" alt="715WQYNTI)B7[2CTDX54KBX.png"/></p><p style="text-align:center"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">图11</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">在“DoHome Upgrade”界面点击“Start upgrading”按钮开始升级。升级结束后按照2.1查看当前Slot，如果Slot=1说明当前固件已经运行在区域1。然后可以继续步骤2.2。</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">如果使用了区域切换固件更新固件到了区域1后，新固件按照下面方法配置连接路由器：</span></p><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">手机连接“Trans-xxxxxx”的热点，会自动弹出路由连接列表，如下图：</span></p><p style="text-align:center">&nbsp; &nbsp; &nbsp;<img src="http://support.doiting.com/static/ueditor/php/upload/image/1567132409760530.png" title="1567132409760530.png"/> &nbsp; &nbsp;</p><p style="text-indent:37px"><span style="font-family: 宋体; text-align: center;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;<span style="text-align: center; font-family: arial, helvetica, sans-serif; font-size: 14px;">图12</span></span></p><p style="text-indent: 37px; text-align: left;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">选择路由后输入密码点击“Join”按钮，即可让设备连接指定路由器。</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.6 无法连接设备热点</span></h3><p style="text-indent:37px"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">重启设备然后再尝试连接</span></p><h3 style="margin-left:0;text-indent:0"><span style="font-family: arial, helvetica, sans-serif; font-size: 16px">3.7 插座硬件接口说明</span></h3><p>芯片型号：ESP-8285，如需帮助，请联系技术邮箱（<strong>support@doit.am</strong>）</p><p style="text-align:center"><img src="http://support.doiting.com/static/ueditor/php/upload/image/1566289948473704.png" title="1566289948473704.png" alt="image.png" height="659"/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</p>
---
layout:     post
title:      Get-Started-S615-CN
subtitle:   Others
date:       2020-04-11
categories: 信息安全
author:     turato
catalog: true
tags:
    - 西门子S615
---
* content
{:toc}

文档翻译

**SIMATI C NET ，Industrial Ethernet Security，SCALANCE S615 Getting Started**

**03/2015      C79000-G8900-C390-01**

## **前言**

**目的**

​	用示例展示 SCALANCE S615 的配置操作

**示例的 IP 设置**

​	注意：下文中的 IP 设置是随意选取的。

​	在真实的网络环境中，你应该调整 IP 设置，以防地址冲突

**通用名词解释**

​	

| 名词             | 含义                         | 中文翻译               |
| ---------------- | ---------------------------- | ---------------------- |
| SINEMA RC        | SINEMA Remote Connect        | 西门子远程连接         |
| SINEMA RC Server | SINEMA Remote Connect Server | 西门子远程连接服务器   |
| S615             | SCALANCE S615                | 西门子S615安全功能模块 |

​	

**更多信息**

除本文外，关于远程网络(Remote Network)还有以下文档可以参考：

- 工业以太网安全-S615基于网络管理的手动配置（Industrial Ethernet Security - SCALANCE S615 Web Based Management）

  本文档旨在为您提供安装，调试和操作设备所需的信息。 它为您提供配置设备所需的信息

- 《工业远程通信-远程控制西门子连接客户端》（Industrial Remote Communication - TeleControl SINEMA Remote Connect Client）

  本手册在安装，配置和运行应用程序SINEMA RC Client时为您提供支持。

-  《工业远程通信-远程控制西门子连接服务器操作说明》（Industrial Remote Communication - TeleControl SINEMA Remote Connect Server" operating instructions）

本手册在安装，配置和运行应用程序SINEMA RC Server时为您提供支持。

- 《工业远程通信入门-远程控制西门子远程连接》（Getting Started Industrial Remote Communication - TeleControl - SINEMA Remote Connect"）
  

根据示例，本文档介绍了SINEMA RC的配置。

- 《 SIMATIC NET工业以太网网络手册》("SIMATIC NET Industrial Ethernet Network Manual")包含有关其他SIMATIC NET产品的信息，您可以将其与该产品系列的设备一起在工业以太网中一起使用。 在那里，您将找到安装所需的通信伙伴的光学性能数据。
  (http://support.automation.siemens.com/WW/view/en/27069465)

获取更多信息，请访问： http://support.automation.siemens.com 

## 1、连接 SCALANCE S615 到广域网

### 1.1 基本步骤

**Structure**

![](\pic\structure.png)

所需组件：

- 1 x S615（附加选项：适当安装的带配件的标准导轨）
- 1 x 24 V 电源供电

- 1 x PC 用来配置 S615

- 符合RJ-45工业以太网标准的网络电缆线，双绞线



**使用的设置**

对于配置示例，设备将获得以下IP地址设置：

![](\pic\SettingUsed.png)

注意：

- 示例中的IP设置是可以自由选择的
- 在真实的网络中，你需要配置IP，以避免可能的地址冲突



**Step in Configuration**

1. 设置 SCALANCE S615  和 网络 （1.2节）

2. 启动网络管理页面（1.3节）

 3. 登录网络管理页面（1.4节）

 4. 改变S615 的IP设置（1.5节）

 5. 配置 S615

    - 指定设备信息（1.6节）
    - 设置时间（1.7节）
    - 创建IP子网（1.8节）

    

### 1.2 设置 S615  和 网络

**步骤**

1，首先打开S615的包装，检查它是否完好无损

2，通电，注意：S615只能在安全超低压运行（SELV）

3，连线，参见1.1中的图

4，通过以太网接口，将S615连接至本地网络( local network)

5，启动设备。默认的LED（F）为红色时，表示连接成功

6，启动PC



### 1.3 启动网络管理页面

在出厂设置中， SCALANCE S615可以通过以下地址访问

- IP地址：192.168.1.1
- 子网掩码：255.255.255.0

1.在管理PC上，使用菜单命令“开始”>“控制”打开控制面板。
2.单击“网络和共享中心”，然后在左侧的导航菜单中选择“更改适配器设置”选项。
3.右键单击“ LAN连接”符号，然后选择“属性”菜单命令。
4.在“本地连接属性”对话框中，启用“ Internet协议版本4”（TCP / IPv4）”复选框。

![1571146374790](\pic\IPconfig.png)

6.单击“确定”确认对话框，然后关闭控制面板。
7.在Web浏览器的地址框中输入IP地址“ 192.168.1.1”。 如果与设备的连接没有问题，则将显示网络管理（WBM）的登录页面。

![1571146374790](\pic\logging.png)





### 1.4 登录网络管理页面

步骤

- 1 ，登录用户：admin，密码：admin，可以修改密码(默认密码admin需要被修改)

- 2，确认弹窗，自动进入更改密码的页面

  ![](\pic\LocalPasswords.png)

- 3，在 "Username" 处选择用户："admin"
- 4，在 "Current Admin Password" 处输入当前密码
- 5，在 "New Password" 处输入新密码
- 6，在 "Password Confirmation"处再次确认新密码

- 7，点击  "Set Values" 按钮

接下来用户admin的密码就被更改为新密码了。改变即可生效。



### 1.5 改变S615的IP设置

步骤

- 1.在导航区域中以及内容区域中的“配置”选项卡上，单击“第3层”>“子网”。
- 2.根据表“使用的设置（1.1节）”输入vlan1的IP地址。
- 3.单击“设置值”。
  IP地址在Web浏览器的地址栏中自动调整。 因为其IP设置不再匹配，所以Admin PC上的Web浏览器无法再访问网络管理页面（WBM）
- 4.在管理PC上，使用菜单命令“开始”>“控制面板”打开控制面板。
- 5.单击“网络和共享中心”，然后在左侧的导航菜单中选择“更改适配器设置”选项。
- 6.在“本地连接属性”对话框中，启用“ Internet协议版本4（TCP / IPv4）”复选框	
- 7.在PC中输入1.1节中的“使用的配置”

![IPconfig2](\pic\IPconfig2.png)

- 8.单击“确定”确认对话框，然后关闭控制面板。
- 9.在Web浏览器的地址框中，输入vlan1的IP地址，请参见表“使用的设置（1.1节）”。 如果与设备的连接没有问题，则将显示Web Based Management（WBM）的登录页面。
- 10.使用用户名“ admin”和修改后的密码登录。



### 1.6 指定设备信息

为了更好地识别SCALANCE S615，请指定设备信息。

1.在导航面板中，在内容区域的“设备”选项卡上单击“系统”>“常规”。
2.在“系统名称”中，输入设备的系统名称，例如 “ S615-1”。
3.在“系统联系人”中输入负责设备的联系人。
4.在“系统位置”中输入设备安装位置的标识符，例如房间号。

![](\pic\device.png)

5.点击 “Set Value”按钮

已经指定了SCALANCE S615的常规设备信息



### 1.7 设置时间

日期和时间保留需要在SCALANCE S615上，以检查证书的有效性（时间）以及日志条目的时间戳。 您可以自己手动设置系统时间，也可以使其与时间服务器自动同步。 对于此示例，使用NTP配置时间服务器。



**注意：**
**手动时间设置，断开电源之后的结果：**
	请注意，如果电源中断，时间将重置为出厂设置。 上电后，您需要再次设置系统时间。 结果，证书可能会失去其有效性。
**使用时间服务器进行同步**
	使用公共时间服务器同步系统时间会在连接上创建其他数据流量。 这可能会导致额外费用，具体取决于您的订户合同

**需要**

- 一台连接到本地网络的NTP服务器

- 该台NTP服务器的IP地址是已知的。

  对于本示例，本地时间服务器的地址是192.168.100.87

**步骤**

1，单击导航区中的“系统”>“系统时间”，然后单击“ NTP客户端”选项卡。
内容区域。

![](\pic\NTPClient.png)

2，在“时区”中，输入当地时间与世界时间（UTC）。 对于中欧
夏令时（CEST）+02：00。

3，在“ NTP服务器IP地址”中，输入IP地址192.168.100.87。 无法输入NTP地址作为主机名。

4，如有必要，请在“ NTP服务器端口”中更改端口。 默认设置为123。
5，在“轮询间隔”(Poll Interval )中，输入同步间隔。 默认设置为64。
6，选择“ NTP客户端”。
7，单击“设置值”。

使用NTP设置系统时间。 单击“刷新”以刷新WBM页面。

![](\pic\ConfigNTPClient.png)



### 1.8 创建子网掩码

接口的处理方式不同。

- 以太网接口P1（vlan1）：连接到LAN
- 以太网接口P5（vlan2）：连接到WAN

对于此配置示例，仅需要配置以太网接口P5的IP子网。 以太网接口P1的IP子网已配置。

**步骤**

- 1.在导航区域中以及内容区域中的“配置”选项卡上，单击“第3层”>“子网”("Layer 3" > "Subnets")。
- 2.对于“接口”，选择“ vlan2”。
- 3.对于“接口名称”，您可以输入一个名称。
- 4.输入vlan2的IP地址，请参阅表“使用的设置（1.1节）”
- 5.单击“设置值”。

![](\pic\vlan2Setting.png)

IP子网被创建，并且展示在“Overview”栏：![](\pic\Overview.png)



## 2、S615 和 SINEMA RC Server 之间的 OpenVPN 隧道

### 2.1 基本步骤

在此示例组态中，使用SCALANCE S615连接了两个分布式站(Station1 , Station2)。 这些设备通过主站中的SINEMA RC服务器( Server )进行通信。

每个SCALANCE S615设备都需要一个KEY-PLUG SINEMA Remote Connect。 `KEY-PLUG`允许从SCALANCE S615到SINEMA RC的连接。

为此，设备需要登录到SINEMA RC Server。 设备和SINEMA RC Server之间的VPN隧道仅在成功通过身份验证后建立.SINEMA RC Server根据配置的通信关系和安全设置连接各个VPN隧道

**Structure**

![](\pic\structure2.png)

**主站（Master Station） - 连接 SINEMA RC Server**

- 在内部网络的测试设置中，网络节点由连接到SINEMA RC Server的LAN端口的PC实施。
  - PC : 作为内部网络3的参与者
  - SINEMA RC Sever

- 通过路由器连接到外部网络
  - 通过连接到SINEMA RC Server 的WAN端口的路由器访问外部网络

**工作站1/2 - 连接到 SCALANCE S615**

- 在内部网络的测试设置中，网络节点由连接到S615的以太网接口P1的PC实施。
  - PC：作为内部网络1/2的参与者
  - S615: 用来保护网络1/2的西门子安全模块
- 通过路由器连接到外部网络
  - 通过连接到S615的以太网接口P5的路由器访问外部网络。

**需要的设备/组件**

需要以下组件完成设置

- 2 x S615（附加选项：适当安装的带配件的标准导轨）
- 2个KEY-PLUG SINEMA RC
- 2 x 24 V电源，带电缆连接器和端子块插头
- 每台2台PC连接到SCALANCE S615。
- 1台装有SINEMA RC Server的PC。
- 1台连接到SINEMA RC Server的PC。
- 3个路由器
- 所需的网络电缆，TP电缆（双绞线）符合工业以太网的IE FC RJ-45标准

**使用的设置**

![](\pic\SettingUsed2.png)





### 2.2 SINEMA RC Server 的访问配置

#### 2.2.1 路由配置

从站和主站位于不同的IP子网中。 为了使从站点可以与主站点进行通信，在S615上创建了合适的默认路由。

**步骤**

1.在Web浏览器的地址框中，输入S615的LAN IP地址，请参阅表“使用的设置（1.1节）”。
2.以“ admin”用户身份和相应的密码登录。
3.在导航区域中单击“第3层”>“路线”（ "Layer 3" > "Routes"）。
4.使用以下设置配置到路由器的路由：

| 目的网络(Destination Network) | 0.0.0.0 (all IP addresses)                      |
| ----------------------------- | ----------------------------------------------- |
| 子网掩码                      | 0.0.0.0                                         |
| 网关                          | 路由的本地网络IP地址根据1.1节中的表“使用的设置” |
| 度量（Metric）                | -1                                              |

5.输入值后，单击“创建”（"Create"）。
6.要更新显示，请单击“刷新”（"Refresh"）。

**结果**

​	创建好了路由：

![](\pic\Routes.png)



#### 2.2.2 激活 IP 伪装

使用IP伪装，以便内部IP地址不会转发到外部。 除此之外，路由器上不需要其他路由设置。

**步骤**

- 1、单击导航区域中的“第3层”>“ NAT”，然后单击内容区域中的“伪装”（"Masquerading"）选项卡。
- 2、为 vlan2 选择“启用伪装”（ "Enable Masquerading"）
- 3、单击“设置值”（ "Set Values"）

**结果**

​	伪装在WAN端口vlan2上被激活。 通过此接口发送数据包时，源地址将转换为分配给vlan2的IP地址。

####  2.2.3 允许访问

为了使 PC 可以访问 SINEMA RC Server，在设备上启用了从 vlan1 到 vlan2 的访问。

**步骤**

- 1、在导航区域中以及内容区域中的“ IP规则”选项卡上，单击“安全”>“防火墙”( "Security" > "Firewall")。
- 2、单击“创建”。 在表中创建一个新条目。
- 3、使用以下设置配置防火墙规则：

| 动作             | 接收                     |
| ---------------- | ------------------------ |
| 出发地           | vlan1 (内部)             |
| 目的地           | vlan2 (外部)             |
| 源地址（范围）   | 0.0.0.0 （所有的IP地址） |
| 目的地址（范围） | 0.0.0.0 （所有的IP地址） |
| 服务             | 所有，默认该服务始终可用 |

- 4、单击“设置值”（ "Set Values"）

**结果**

由于此防火墙规则，vlan1和vlan2之间的所有服务都可以不受限制地进行，例如 HTTPS

![](\pic\IPRules.png)

### 2.3 SINEMA RC Server 的远程连接配置

#### 2.3.1 创建节点组

可以将用户和设备放到参与者组中。 您还可以指定允许还是禁止单个组的参与者之间的通信。

对于此样本配置，将创建以下组。

- Station -1

- Station-2

- Service



**需要**

- The SINEMA RC Server 连接到广域网（WAN）

**步骤**

1、在Web浏览器的地址框中，输入SINEMA RC Server 的WAN IP地址“ https：// <WAN IP地址>”，请参阅表“使用的设置（2.1节）”。
2、以“ admin”用户身份登录并使用相应的密码。
3、在导航区域中，单击“远程连接”>“参与者组”（ "Remote connections" > "Participant groups"）。 内容区域中列出了已经创建的参与者组。
4、单击“创建”（ "Create"）。 打开“新参与者组”（ "New participant group"）页面。
5、输入“ Station 1”作为组名，然后单击“退出”。
6、对组“ Station-2”和“Service”重复步骤1-3。

**结果**

![](\pic\ParticipantGroups.png)



#### 2.3.2 创建设备

1.在导航区域中，单击“远程连接”>“设备”。 内容区域中列出了已创建的设备。
2.单击“创建”按钮创建一个新设备。
3.输入设备的设备名称，例如 站1的“ S615-1”和站2的“ S615-2”
4.单击“继续”。
5.启用选项“连接本地子网”
6.使用以下设置配置设备：

| 本地局域网IP地址（Local LAN IP address） | vlan1的IP地址参见表“使用的设置” |
| ---------------------------------------- | ------------------------------- |
| 网络掩码                                 | 255.255.255.0                   |

7.单击“继续”（ "Continue"）。 显示“组成员身份”（"Group memberships"）选项卡。
8.启用适当的组。
对于“ S615-1”设备，组“ Station 1”
对于“ S615-2”设备，组“ Station 2”
9.单击“继续”（ "Continue"）。 显示“密码”（"Password"）选项卡。
10.指定访问密码，例如 S615-1为An:t_010，S615-2为An:t_020。
密码必须由大写和小写字母，数字和特殊字符组成。
11.单击“退出”。

**结果**

设备与已创建的设备一起列出。

- 设备密码
- 设备ID
- 指纹

您将在设备信息中找到设备ID和指纹。 点击”感叹号“以打开设备信息。

![](\pic\Devices-S615-1.png)

#### 2.3.3 配置通讯关系

为了使参加者群体能够彼此交流，交流关系是必要的。 可以为每个方向创建通信关系。

对于此样本配置，将创建以下通信关系：

| 来自组    | 到目的地组 |
| --------- | ---------- |
| Service   | Station-1  |
| Service   | Station-2  |
| Station-1 | Station-2  |

在此组态示例中，通信仅从组“ Station 1”到组“ Station 2”。 相反，则无法进行通信。 对于从“站2”组到“站1”组的通信，需要另一个通信关系。

“服务”组还可以与“站1”和“站2”组进行通信，但通信不能反过来（也就是站1和站2不能向服务组发送数据）。



**步骤**

- 1.在导航区域中，单击“远程连接”>“参与者组”（ "Remote connections" > "Participant groups"）。 内容区域中列出了已经创建的参与者组。
- 2.对于“工作站1”，单击“操作”（"Actions" ）列中的符号。 打开“目标组”页面。（"Destination group"）
- 3.启用“ Station 2”，然后单击“保存”。
- 4.单击“退出对话框”。
- 5.对于“服务”，单击“操作”列中的符号。 打开页面“目标组”。
- 6.启用“站1”和“站2”。 点击“保存”。
- 7.单击“退出对话框”

**结果**

​	创建了通信关系

![](\pic\CommunicationRelationships.png)



### 2.4 S615 的远程连接配置

#### 2.4.1 带指纹的安全 OpenVPN 连接

**要求**

- 在PC1 / 2上，打开两个Web浏览器窗口。
- Web浏览器1：
  您以`admin`身份登录到S615的`WBM`。
- Web浏览器2：
  您以用户`service`或`admin`的身份登录到`SINEMA RC Server`的`WBM`。
- 在`S615`中插入了有效的`KEY-PLUG`。

**步骤**

1.切换到Web浏览器1。
- 在Web浏览器的地址框中，输入S615的LAN IP地址，请参见表“使用的设置（2.1节）”。
-  以`admin`用户身份登录并使用相应的密码。
-  在导航区域中单击 “System”>“ SINEMA RC”。
-  对于“ SINEMA RC地址”，输入SINEMA RC服务器的WAN IP地址，请参见表“使用的设置（2.1节）”。

2.切换到Web浏览器2
- 在Web浏览器的地址框中，输入`SINEMA RC Server`的WAN IP地址，请参见表“使用的设置（2.1节）”。
- 以`admin`用户身份和相应的密码登录。
- 在导航区域中，单击"Remote connections" > "Devices"。
- 单击`Actions`中的符号以打开设备信息。
- 按住鼠标左键，选择设备ID条目。
- 右键单击所选内容，然后在快捷菜单中选择复制命令。

3.切换到Web浏览器1。
- 右键单击`Device ID`的输入框。
- 在快捷菜单中，选择要插入的菜单命令。
- 在`Device Password`中，输入为访问配置的密码，对于S615-1，输入An:t_010，对于S615-2，输入At:t_020。
- 启用“自动防火墙/ NAT规则”。
启用后，将自动创建合适的NAT和防火墙规则。对于“Verification Type”（验证类型），请选择“Fingerprint”（指纹）。

4.切换到Web浏览器2。
- 按住鼠标左键，选择指纹条目。
- 右键单击所选内容，然后在快捷菜单中选择复制命令。

5.切换到web浏览器1。

- 右键单击`Fingerprint`输入框。
- 在快捷菜单中，选择要插入的菜单命令。
- 选择`Enable SINEMA RC`，然后单击“设置值”。

![SINEMARemoteConnect](\pic\SINEMARemoteConnect.png)



**结果**

设备将建立到SINEMA RC服务器的OpenVPN隧道。您可以登录WBM以查看连接是否成功。
Web浏览器1：在导航区域中，单击“Information”>“ SINEMA RC”

![SINEMA-RCInformation](/pic/SINEMA-RCInformation.png)

web浏览器2: 在导航区点击 "Remote connections" > "Devices" 
![RemoteConnectionDevices](/pic/RemoteConnectionDevices.png)



#### 2.4.2 带 CA 证书的安全 OpenVPN 连接

##### 2.4.2.1 加载证书

**需求**
●在`S615`和`SINEMA RC Server`上设置了正确的时间。
●在PC1 / 2上，分别打开两个Web浏览器窗口。
●Web浏览器1：
您以“ admin”身份登录到S615的WBM。
●Web浏览器2：
您以“ admin”用户身份登录到SINEMA RC Server的WBM。

**步骤**
1.切换到Web浏览器2。
-在Web浏览器的地址框中，输入SINEMA RC的WAN IP地址。
服务器，请参见表“使用的设置（2.1节）”。
- 以“ admin”用户身份和相应的密码登录。
- 单击导航区域中的“Security”>“Certificates”。
- 单击“操作”中的符号以导出证书。

2.切换到Web浏览器1。
- 在Web浏览器的地址框中，输入S615的LAN IP地址，请参见表“使用的设置（2.1节）”。
- 以`admin`用户身份登录并使用相应的密码。
- 在导航区域中以及内容区域中的“ HTTP”选项卡上，单击“System”>“Load & Save”。
- 单击“ X509Cert”旁边的“Load”按钮。打开用于加载文件的对话框。
- 导航到导出的服务器证书。在对话框中单击“打开”按钮。
现在，文件已加载到设备上。成功加载后，单击“确定”确认下一个对话框。

**结果**
证书被加载。进入"Security"->"Certificates",你可以看到所有证书。被加载的证书的状态必须为“valid”。

![1572509713407](/pic/CertificatesOverview.png)

##### 2.4.2.2 配置 SINEMA RC Server 的OpenVPN连接

**要求**

- 在S615上插入有效的`KEY PLUG`

**步骤**

1.切换到Web浏览器1。
- 在导航区域中单击“System”>“ SINEMA RC”。
- 对于“ SINEMA RC地址”，输入SINEMA RC服务器的WAN IP地址，请参见表“使用的设置（2.1节）”。

2.切换到Web浏览器2。
- 在导航区域中，单击“Remote Connections”>“Devices”。
- 单击“Action”（操作）中的符号` ！`以打开设备信息。
- 按住鼠标左键，选择设备ID条目。
- 右键单击所选内容，然后在快捷菜单中选择复制命令。

3.更改为Web浏览器1。
- 右键单击`Device ID`的输入框。
- 在快捷菜单中，选择要插入的菜单命令。
- 在`Device Password`中，输入为访问配置的密码，对于S615-1，输入An:t_010，对于S615-2，输入An:t_020。
- 启用“自动防火墙/ NAT规则”。
启用后，将自动创建合适的NAT和防火墙规则。在“验证类型”中，选择“ CA证书”。
- 在“ CA证书”中选择服务器证书。 只能选择已加载的证书

![SINEMA-RC-Conection2](/pic/SINEMA-RC-Conection2.png)

- 选择“Enable SINEMA RC” ，点击 “Set Values”



**结果**

设备将建立到SINEMA RC服务器的OpenVPN隧道。您可以登录WBM以查看连接是否成功。
Web浏览器1：在导航区域中，单击“Information”>“ SINEMA RC”。

![SINEMA-RC-ConectionInformation2](/pic/SINEMA-RC-ConectionInformation2.png)



web浏览器 2: 在导航区域点击 "Remote connections" > "Devices" 

![RemoteConnectionsDevices2](/pic/RemoteConnectionsDevices2.png)



## 附录

### KEY PLUG

KEY-PLUG 存储SCALANCE W组件的组态数据。还支持其它信息安全功能和iFeatures。

KEY-PLUG（or C-PLUG）用于替换设备，将旧设备的配置信息传送到新设备。

除此之外，若模块出现故障，还可简便、快速地更换模块，无需重新组态替换设备，也无需对人员专门进行培训。需要更换设备时，可以从故障部件简单地拆下KEY-PLUG，然后将其插到替换设备中。然后，安装在网络或自动化系统中的更换设备会以故障设备相同的设备组态自动启动。 

**注意**

在操作过程中，请勿拆卸或插入KEY-PLUG！仅在关闭设备电源后才能卸下或插入KEY-PLUG。

设备会每隔一秒检查一次PLUG。 如果检测到PLUG已卸下，则将重新启动。

如果在设备中插入了有效的KEY-PLUG，则设备在重启后将变为已定义的错误状态。



当新设备使用PLUG启动时，它将自动以与旧设备完全相同的配置继续运行。如果IP配置是通过DHCP设置的，并且尚未相应地重新配置DHCP服务器，则IP配置就会出现异常。

如果使用基于MAC地址的功能，则需要重新配置。
如果插入了错误的PLUG（例如来自其他产品的PLUG）或损坏的PLUG，则设备会通过“ F” LED发出错误信号。

您可以再次删除PLUG，也可以选择重新格式化PLUG的选项。

就PLUG而言，设备以两种模式工作：

- 不使用PLUG设备会将配置存储在内部存储器中。未插入PLUG时，此模式有效。
- 使用PLUG时，存储在PLUG中的配置显示在 WBM （Web Browser Management）的“信息> PLUG”中。如果对配置进行了更改，则设备会将配置直接存储在PLUG和内部存储器中。插入PLUG后，此模式即激活。使用插入的PLUG启动设备后，设备将使用PLUG上的配置数据启动。

**KEY-PLUG 上的许可信息**

根据配置，KEY-PLUG 也包含许可信息，允许使用 西门子远程服务（Siemens Remote Services）

| 种类     | 属性                                                         | 编号          |
| :------- | :----------------------------------------------------------- | :------------ |
| C-PLUG   | 可交换存储介质（32 MB），用于配置数据                        | 6GK1900-0AB00 |
| C-PLUG   | 可交换存储介质（256 MB），用于配置数据                       | 6GK1900-0AB10 |
| KEY-PLUG | 可交换存储介质（256 MB），用于启用到SINEMA RC的连接功能并接受配置数据。 | 6GK5908-0PB00 |

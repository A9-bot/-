1、开通腾讯云服务器，创建实例



远程登录后查看内网网卡信息



![4f693aed-edd1-4a2f-b46c-9a8d2610d687](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/4f693aed-edd1-4a2f-b46c-9a8d2610d687.png)

2、ikuai的前置工作



虚拟机安装ikuai 32位版本，系统选Linux，内存2G，硬盘5G，*不拆分磁盘*。

创建完成后，加载iso文件，添加一张网卡，选桥接模式。

将后添加的网卡设为lan1口，用来本地配置前置工作

设置lan1的地址

![008c6aa3-5004-4407-83de-61c48203ca8b](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/008c6aa3-5004-4407-83de-61c48203ca8b.png)



本地计算机访问lan1地址

![2a724fdd-168f-4ae5-8e80-187902b6b265](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/2a724fdd-168f-4ae5-8e80-187902b6b265.png)



将最开始的网卡设为桥接模式，在高级里更改它的mac地址为云服务器内网网卡的mac地址

![100b0e0f-94cd-492c-8416-6cb3f5e18832](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/100b0e0f-94cd-492c-8416-6cb3f5e18832.png)





在浏览器里配置wan口

![8fd88460-19c7-47df-a5a5-46a77bb53bda](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/8fd88460-19c7-47df-a5a5-46a77bb53bda.png)



查看ikuai信息显示



![56187059-01c7-400e-88bc-a5ebc124f7ed](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/56187059-01c7-400e-88bc-a5ebc124f7ed.png)



配置DNS

![68d6b67e-be19-4c4b-9e19-74ffd0b92d7c](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/68d6b67e-be19-4c4b-9e19-74ffd0b92d7c.png)



开启外网访问许可

![cd8735d1-3cb4-4e38-ba2a-a8cd9ab3abdf](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/cd8735d1-3cb4-4e38-ba2a-a8cd9ab3abdf.png)



3、将ikuai挂载到腾讯云服务器上





开启对象存储服务，创建存储桶

![db593910-818b-4c1e-b029-81ebe66631b0](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/db593910-818b-4c1e-b029-81ebe66631b0.png)



复制临时链接用于创建自定义镜像

![f0857d79-d3da-46cf-b6c4-57efaccc6fa3](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/f0857d79-d3da-46cf-b6c4-57efaccc6fa3.png)



创建镜像（注意选择强制导入）

![840552c1-06e8-4022-83b1-47e08bd66946](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/840552c1-06e8-4022-83b1-47e08bd66946.png)



重装实例系统，选择创建的镜像

![9a840b04-ef5f-4b60-8045-b2e8ce80c537](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/9a840b04-ef5f-4b60-8045-b2e8ce80c537.png)







4、通过公网ip访问ikuai进行配置

![85e68a0e-06d9-423a-adb8-2b23e7cad5f9](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/85e68a0e-06d9-423a-adb8-2b23e7cad5f9.png)





开启VPN服务

![5ff1fadb-4541-474c-9b7d-a49be0fdf5ec](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/5ff1fadb-4541-474c-9b7d-a49be0fdf5ec.png)



导出配置文件，修改配置文件后缀为.ovpn，修改文件中ip为公网ip



创建账号

![cad22770-e1e0-4a02-9266-c7e6f55ce4bf](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/cad22770-e1e0-4a02-9266-c7e6f55ce4bf.png)



安全组添加两条规则开放协议端口

![4eabb541-541b-4f5e-8200-7c52dc9dbb37](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/4eabb541-541b-4f5e-8200-7c52dc9dbb37.png)



计算机通过openvpn客户端导入配置文件后接入VPN

![5d166d1d-316c-4a0c-a66c-efbaa1afc9d0](file:///C:/Users/%E5%8F%8C%E7%9E%B3/Pictures/Typedown/5d166d1d-316c-4a0c-a66c-efbaa1afc9d0.png)



其它计算机如法炮制





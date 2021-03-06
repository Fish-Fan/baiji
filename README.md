## 基于VirtualBox + Ubuntu16.04 的 PouchContainer 体验环境搭建与上手
### 上手前准备
1. VirtualBox </br>
  下载地址:https://www.virtualbox.org/
2. 下载Ubuntu镜像 </br>
  下载地址：
### 安装VirtualBox
安装完之后如下（当前版本号为5.2.16）：

![virtualbox_install_success](https://user-images.githubusercontent.com/16412949/43075642-ee1277c4-8eb3-11e8-8468-e7dd6f89a519.jpg)

### 新建虚拟机（Mac版本操作参照windows）
1. 新建系统要选择Ubuntu-64bit(版本号为16.04)
2. 新建虚拟机请选择专家模式

    ![expert_mode](https://user-images.githubusercontent.com/16412949/43078120-1956fccc-8ebc-11e8-97ee-b634893f0435.jpg)

3. 分配内存推荐为2G(2048M)
4. 虚拟硬盘选择 **使用已有的虚拟硬盘文件** </br>

    ![new_virtual_machine](https://user-images.githubusercontent.com/16412949/43075975-25046d90-8eb5-11e8-8687-c588d2396d21.jpg)

### 启动虚拟机
  虚拟机成功启动之后，输入初始的用户名和密码
  + 用户名：pouch
  + 密码：123456

### 启动pouch服务(默认开机启动)

  ```
  systemctl start pouch
  ```

  注意事项：需首先切换至root用户，否则会提示权限不足

  启动成功如下:

  ![start_pouch_service](https://user-images.githubusercontent.com/16412949/43077720-e7ad3796-8eba-11e8-978a-26be58989c80.PNG)

### 启动一个busybox基础容器

  ```
  pouch run -t -d busybox sh
  ```

  启动成功如下：

  ![new_busybox_container](https://user-images.githubusercontent.com/16412949/43078533-539592b2-8ebd-11e8-8254-66aa56f12775.PNG)

### 登入启动容器

  ```
  pouch exec -it {ID} sh
  ```

  注意事项：ID为上条命令输出的完整ID中的前六位,如

  ```
  pouch exec -it 81d749 sh
  ```

  执行成功如下:

  ![login_pouch_container](https://user-images.githubusercontent.com/16412949/43078850-2ab70938-8ebe-11e8-8c39-bbf9121f7dfb.PNG)

  至此，你已经建立了一个可交互容器的实例。

## Quick Start for building PouchContainer environment based on VirtualBox & Ubuntu16.04
### Before Start
1. Download VirtualBox:
Download here: https://www.virtualbox.org/
2. Download Ubuntu mirror:
Download here: https://www.virtualbox.org/
### Install VirtualBox
Installing the virtualbox,you can see the picture as follows (Current Version: 5.2.16)

![create_virtual_machine](https://user-images.githubusercontent.com/16412949/43110939-36cdadcc-8f21-11e8-9885-b753198d88f4.jpg)

### Create New Virtual Machine In VirtualBox
1. Select the Ubuntu-64bit
2. Choose the expert Mode like this

    ![choose_expert_mode](https://user-images.githubusercontent.com/16412949/43111016-aa1b2de0-8f21-11e8-9f29-de836d764583.jpg)

3. Allocation of memory is recommended as 2G(2048M)
4. Use an existing virtual hard disk file

    ![install_virtualbox](https://user-images.githubusercontent.com/16412949/43110952-484f870a-8f21-11e8-84c3-38a45957ee7b.jpg)

### Run Virtual Machine
When all thing start up, input the origin username and password
+ username: pouch
+ password: 123456

### Start PouchContainer

```
systemctl start pouch
```

Note: You need to switch to root user or you will get an permission deny error.

After successfully start the pouchContainer, you wil get the result like this

![new_busybox_container](https://user-images.githubusercontent.com/16412949/43078533-539592b2-8ebd-11e8-8254-66aa56f12775.PNG)

### Login PouchContainer

```
pouch exec -it {ID} sh
```

Note: ID is the first six of the complete ID in the output of the last command, such as

```
pouch exec -it 81d749 sh
```

After that, it should be like this

![login_pouch_container](https://user-images.githubusercontent.com/16412949/43078850-2ab70938-8ebe-11e8-8c39-bbf9121f7dfb.PNG)

Finally, you have build an instance of interactive pouchContainer.

### Feedback
We hope this guide would help you get up and run with PouchContainer. And feel free to send feedback via ISSUE, if you have any questions. If you wish to contribute to PouchContainer on this guide, please just submit a pull request.

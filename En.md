##
### Before Start
1. Download VirtualBox: </br>
  Click here to download VirtualBox: :https://www.virtualbox.org/
  Download Ubuntu mirror: </br>  
  Click here to download Ubuntu mirror:
  https://www.virtualbox.org/

2. Install VirtualBox
  Installing the virtualbox,you can see the picture as follows (Current Version: 5.2.16)

  ![create_virtual_machine](https://user-images.githubusercontent.com/16412949/43110939-36cdadcc-8f21-11e8-9885-b753198d88f4.jpg)

3. Create New Virtual Machine In VirtualBox
  1. Select the Ubuntu-64bit
  2. Choose the expert Mode like this

        ![choose_expert_mode](https://user-images.githubusercontent.com/16412949/43111016-aa1b2de0-8f21-11e8-9f29-de836d764583.jpg)

  3. Allocation of memory is recommended as 2G(2048M)
  4. Use an existing virtual hard disk file

        ![install_virtualbox](https://user-images.githubusercontent.com/16412949/43110952-484f870a-8f21-11e8-84c3-38a45957ee7b.jpg)

4. Run Virtual Machine
  When all thing start up, input the origin username and password
  + username: pouch
  + password: 123456

5. Start PouchContainer

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

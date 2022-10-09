# Documentation-of-M1-MacBook-to-use-QT-PY-2040
## Platform:

**OS:** macOS Monterey Version 12.6

**Processor:** Apple M1 Pro

**Laptop model:** MacBook Pro (14-inch, 2021)

## Installed Software:

1. `Homebrew` 
2. `cmake`
3. `ArmMbed/homebrew-formulae`
4. `arm-none-eabi-gcc`
5. Terminal_Rosetta2

## Guide:

### Step#1: Running Your Terminal Under the Rosetta 2

1. Open your **Finder** on your mac and choose the **Application** icon at left side. Then select and open the folder called **utility**.

![Screen_Shot_2022-10-09_at_14 51 44](https://user-images.githubusercontent.com/105755054/194780832-8c683f7e-2587-473b-9cdc-1c30b5516ad0.png)


2. When you open this folder you can find the Terminal, then right click to **Duplicate** and rename it called Terminal_Rosetta. It may request you enter password of you Admin. 

![Screen_Shot_2022-10-09_at_14 58 56](https://user-images.githubusercontent.com/105755054/194780855-566ed420-3b15-4e24-a73d-6321c7a13fd7.png)
    
3. After that you will have two Terminals in this folder, and right click Rosetta one choosing **Get Info**.
    
![Screen_Shot_2022-10-09_at_15 00 06](https://user-images.githubusercontent.com/105755054/194780869-4c35fbdc-6a63-47d2-a17d-21cfb090c2cb.png)
    
4. After you clicked **Get Info**, this window will jump out. At this window, select Open using Rosetta. Finally, you will have a Terminal running under x86 version.
    
![Screen_Shot_2022-10-09_at_15 01 42](https://user-images.githubusercontent.com/105755054/194780952-3a612e03-ff45-482d-917e-8b008fc51df2.png)

---

## Step#2: Install `Homebrew` On Your Mac

In this part I will use `bash` as example to show the demo. You can see at the top of the Terminal whether you're using `zsh` or `bash`. If your Terminal is `zsh` you can just type in `bash`, and it will convert to bash one.

![Screen_Shot_2022-10-09_at_15 11 47](https://user-images.githubusercontent.com/105755054/194780996-3b41b68b-41c2-4192-ba48-ce8dd95b50da.png)

1. You can visit the [Homebrew official website](https://brew.sh/) to install it, or just copy and past `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` this command to your Terminal. Then the Homebrew will install on your mac automatically. Notice that since I have already installed Homebrew, when I run this command, it will update my Homebrew. But if you never use it, you have to do more steps to set the path of Homebrew. The set-up command will show you at the marked red box and you can just copy and past some commands to set the path.
    
![image](https://user-images.githubusercontent.com/105755054/194781023-9a4b84ba-6700-4c86-a168-43d8eac0a71a.png)

2. Verify : type`$ brew` in your command line and press enter. If you successfully install, your interface will look like this.
    
![Screen_Shot_2022-10-09_at_15 31 19](https://user-images.githubusercontent.com/105755054/194781029-ba1bd2b1-bda4-46ef-8d2a-ff3da3428faa.png)

3. Also you can use `$ brew list` to display all software you download.
        
![Screen_Shot_2022-10-09_at_15 38 03](https://user-images.githubusercontent.com/105755054/194781040-67627b66-7c21-43a5-a994-463cd8912a76.png)
 
---
    
## Step#3: Install `cmake` `tap ArmMbed/homebrew-formulae` `arm-none-eabi-gcc`
    
1. Using these command individually: 
    
`$ brew install cmake`

![Screen_Shot_2022-10-09_at_15 43 49](https://user-images.githubusercontent.com/105755054/194781317-89e7d9b8-516b-44cf-ba2e-579f08ba30b5.png)

`$ brew tap ArmMbed/homebrew-formulae`

![Screen_Shot_2022-10-09_at_15 44 50](https://user-images.githubusercontent.com/105755054/194781326-11fe3322-df38-4f29-8b78-485a88d3d131.png)
    
`$ brew install arm-none-eabi-gcc`
    
![Screen_Shot_2022-10-09_at_15 46 08](https://user-images.githubusercontent.com/105755054/194781118-8dee69cb-76ad-467a-950f-5c94df7f6d54.png)

Because I've already installed them all, they won't be installed when I type these commands, they'll be checked for updates.
    
2. Verify your installed Software, using `$ brew list` to check them
   
![Screen_Shot_2022-10-09_at_15 48 49](https://user-images.githubusercontent.com/105755054/194781123-b90e51ee-729b-4e55-b977-c5b0405b6e61.png)

    
---
    
## Step#4: Get the SDK and Examples
    
1. Using these commands to create a folder called pico
        
`$ cd ~/`
        
`$ mkdir pico`
        
`$ cd pico`
        
After running these commands above you can find there is a new folder called pico on your mac, and you can find it by following this path:
        
Finder→Macintosh→Users→ **Your user name of your computer** (yuchenwang) →pico
        
![Screen_Shot_2022-10-09_at_15 56 02](https://user-images.githubusercontent.com/105755054/194781494-98662ef9-bfff-47da-a44d-c3ef8899ab86.png)
        
![Screen_Shot_2022-10-09_at_15 57 27](https://user-images.githubusercontent.com/105755054/194781499-c57fd74f-925d-4067-8f56-c96da1a22291.png)
        
![Screen_Shot_2022-10-09_at_15 58 47](https://user-images.githubusercontent.com/105755054/194781503-126d5ff9-1bb8-4c1b-b6aa-ac072b71ec3f.png)
        
        
2. Clone the **pico-sdk** and **pico-examples** from website
        
`$ git clone -b master https://github.com/raspberrypi/pico-sdk.git`
        
`$ cd pico-sdk`
        
`$ git submodule update --init`
        
`$ cd ..`

`$ git clone -b master https://github.com/raspberrypi/pico-examples.git`
        
After using those commands above you will find there are two new folders in your pico, one called **pico-sdk** and the other one called **pico-examples**
        
![Screen_Shot_2022-10-09_at_16 03 27](https://user-images.githubusercontent.com/105755054/194781788-394fbe5d-684e-4e34-8902-100f8fcf833e.png)

---
        
## Step#5: Create ‘build’ Folder and Set the PICO_SDK_PATH
        
1. Using these command one by one to create a new folder called **build** under the **pico-examples** folder, then entering this new folder
        
`$ cd pico-examples`

`$ mkdir build`

`$ cd build`
        
![Screen_Shot_2022-10-09_at_16 08 35](https://user-images.githubusercontent.com/105755054/194781847-0b659905-87c3-4e3e-b7f2-32c233bbe7f7.png)

1. set the path of tools. Using this command below to set the path to this folder
`$ export PICO_SDK_PATH=../../pico-sdk`
2. Then  use `$ cmake ..` to verify your setting, if you are successfully set the path, it will look like this. Notice that your have to move in **build** folder. Using `$cd pico/pico-examples/build` to enter this folder
            
![Screen_Shot_2022-10-09_at_16 20 05](https://user-images.githubusercontent.com/105755054/194781855-09540e60-c502-4d5f-9983-326d3377d733.png)

---
        
## Step#6: Make ‘Hello_World’
        
1. Stay at ‘build’ folder and enter a next folder called ‘hello_world’ with command `$cd hello_world` , then using  `make -j8` to make the executable file for RP 2040. Please note that if you are compiling this file for the first time, your window may be different from mine, since I have already compiled it once
            
![Screen_Shot_2022-10-09_at_16 27 18](https://user-images.githubusercontent.com/105755054/194781866-14a7fbce-86b7-417b-8dd4-c3a0f0b6ac76.png)
        
---
        
## Step#7: Move the Executable File to QT-PY 2040
        
1. Connect QT-PY 2040 with your Mac, and there is a new usb popup on your Mac 

![Screen_Shot_2022-10-09_at_16 44 22](https://user-images.githubusercontent.com/105755054/194781874-42e03bc2-dce8-4ddb-ab93-726b047a2701.png)

Then moving the file call ‘hello_usb.uf2’ to this usb, and ‘RPI-RP2’ will eject automatically.
        
![Screen_Shot_2022-10-09_at_16 45 26](https://user-images.githubusercontent.com/105755054/194781885-7871d62a-2c45-4120-9384-27da5b7055e2.png)
        
---
## Step#8: See ‘Hello World!’

1. Open your Terminal again and entering `$ ls /dev/tty.*` you can see your device’s name called **usbmodem101**
            
![Screen_Shot_2022-10-09_at_16 51 40](https://user-images.githubusercontent.com/105755054/194781895-fc68bd4d-73f8-4038-9e90-58d8b1b062af.png)
            
2. Open the serial monitor with command `$ screen /dev/tty.usbmodem101 115200`

![Screen_Shot_2022-10-09_at_16 56 33](https://user-images.githubusercontent.com/105755054/194781905-8a7fa9b3-8077-474e-8935-b7ad6c509e13.png)

3. Finally, you will see ‘Hello , world!’ on your Terminal.

![Screen_Shot_2022-10-09_at_17 01 08](https://user-images.githubusercontent.com/105755054/194781912-8da873f7-d3fe-427d-9992-5994d3c7d5b7.png)

---
        
## Summary :
        
 A lot of the time unix code is very close to Linux code, you can use Linux instruction directly to guide yourself, but be aware that some of the common code is not interlinked, such as `apt-get` , but we can use `brew install` or `wget`. For serial monitor part, I recommend to use `$ screen`, but you have to check the device’s name first, and different ports you choosing, different names are assigned to it. Additionally, if you are not familiar with Terminal command to create folder or move files, you could open the folder directly on your Finder to see what’s going on, after you using some specific commands, which is really helpful to visualize the tedious code.

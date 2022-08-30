# Create a custom Raspberry pi OS image and clone to SD card
**Pre Requisites**
You need to have a linux environment with gparted installed. If you are on a Mac or Windows, You will have to quickly download virtualbox and run an ubuntu instance.Using anypro will more recommend because it will directly using Ubuntu environment can more easily.

1. Open your Ubuntu terminal.
Manage Partitions with GParted How-to is a practical, hands-on guide providing you with step-by-step instructions to effectively organize your hard drive.
```sudo apt-get install gparted```

2. Insert SD card,it is already have a raspberry pi os.we can look our disk
```sudo fdisk -l```
3. Now we need to completely clone the SD card and we do it using the follow command.
```sudo dd if=/dev/sdb of=*your_want_image name.img*```

    ( Ex.Before,it is often called "sphereSD_v2.0.4.img" )
    
    
    **```if```**  stands for input file which is my disk path /dev/sdb.

    **```of```** stands for output file, which you can give any name you specify.
    
    *This process will take some time as it will copy what’s in your memory card block by block.
    
4. Compressing the Image file with pishrink

    ```wget https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh```
    
    ```chmod +x pishrink.sh```
    
    ```sudo mv pishrink.sh /usr/local/bin```

5. In order to compress image,run the following

    ```sudo pishrink.sh (old_file_name.img)    (new_file_name.img) ```
    
    
    This will also take some time and finally it will give you an output saying how much your initial image was shrunk in the new file.
    
6. Copy the image to new SD Card

This is relatively easy. Download the [Etcher](https://www.balena.io/etcher/) application for your OS and select your newly shrunken image, then select the new SD card and click the button Flash And you are all good.Suggest your operate is in Ubuntu environment otherwise it could have some error.
- Download for Linux x64(64-bits)(Appimage)

- To Unzip this new file.
- If you can’t Run AppImage on Ubuntu 22.04? Run the following to Fix it

    ```sudo apt install libfuse2```
    
- Find a file,such as (balenaEtcher-1.7.9-x64.Appimage) and click your mouse right button,find a permissions to fix some content.
 ![](https://s3.ypcloud.com/hackmd/uploads/upload_6e5676073e8288415b45256d4a7fab70.png)
 *Check Allow executing file as program
 
 
![](https://s3.ypcloud.com/hackmd/uploads/upload_6b0b1cd70c3213784ad403bf72fe9745.png)

![](https://s3.ypcloud.com/hackmd/uploads/upload_c4587728bc2923d3b20e181f12200ca4.png)

![](https://s3.ypcloud.com/hackmd/uploads/upload_2f75a65db0442e71a47d20c75372d8f2.png)

~Finished~

- But you need to test because it still can't ensure the clone success.
- So pick up your new clone SD card and insert your raspberry pi and restart your device.
- If clone success,you will have a normal boot procedure . 





















    
    
    
 



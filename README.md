# Xperia 10 II: How to use the Recovery Mode


If your Xperia 10 II is not starting up normally or not starting up at all, you can attempt to fix your device with the help of the Recovery Mode. This article will provide you with step-by-step instructions on recovering a malfunctioning device.

**NOTE:** _This article is for Xperia 10 II only. There are separate articles for all other Xperias, Jolla Phone, Jolla C (also Aqua Fish) and for Jolla Tablet:_

- Xperia X, XA2, 10: [**https://jolla.zendesk.com/hc/en-us/articles/360002996893**](https://jolla.zendesk.com/hc/en-us/articles/360002996893)
- Jolla Phone: [**https://jolla.zendesk.com/hc/en-us/articles/204709607**](https://jolla.zendesk.com/hc/en-us/articles/204709607)
- Jolla C &amp; Aqua Fish: [**https://jolla.zendesk.com/hc/en-us/articles/115000663928**](https://jolla.zendesk.com/hc/en-us/articles/115000663928)
- Jolla Tablet: [**https://jolla.zendesk.com/hc/en-us/articles/208406917**](https://jolla.zendesk.com/hc/en-us/articles/208406917)



## **1 What is the Recovery Mode?**

**Recovery Mode** is a tool designed to help your device recover from critical errors. It is somewhat &quot;hidden&quot;, because you are not meant to have to use it except in case of a rare device malfunction. To use it successfully you need a MicroSD card in your device.

Recovery Mode is considered a last resort and should be used only if there is no other way.
 It is a powerful tool and using it always means that your data on the device is at risk.
 Please read the instructions in this article carefully.

**NOTE** :  You can install Sailfish X again (&quot;re-flash&quot;)  to your Xperia device. This is an effective way to resolve many kinds of problems, compared to Recovery Mode. Your Sailfish X license even entitles you to download a more recent Sailfish version from [**Jolla Shop**](https://shop.jolla.com/downloads/) **. ** On the other hand, flashing implies that all data and apps in the device will be wiped away and lost. Please consider which way suits better to you.

If at any point you are uncertain about using Recovery Mode, please [**contact us**](https://jolla.zendesk.com/hc/en-us/requests/new).

### **1.1 When should I use Recovery Mode?**

- You are experiencing problems starting up your device.
- Your device doesn&#39;t start past the Sony logo.
- Your device seems to never complete the startup process, before restarting again (AKA &quot;boot loop&quot;, starts up to &quot;Sony logo&quot; but no further).
- Your device starts up to a state where it is unusable because of a corrupted or not visible user interface.
- Some parts of the Sailfish OS system seem to be missing. For example, opening Settings crashes the phone or Settings opens as a blank screen.
- You were instructed by Jolla&#39;s Service &amp; Support personnel to use it.



## **2 Setting up Recovery Mode**

### **2.1 Forcing Xperia to Recovery Mode**

- Disconnect USB cable from Xperia
- Turn Xperia OFF
- If you have the _fastboot drivers_ (Windows) or _fastboot tools_ (Linux, Mac) already installed on your computer, skip to the next step. You have them if you installed Sailfish OS to your Xperia with the present computer.
 If not, install _fastboot_ now - the instructions are:
  - Windows computer: chapter 2 in [**Sailfish X instructions - Windows**](https://jolla.com/sailfishx-windows-instructions/))
  - Linux computer: chapter 2 in [**Sailfish X instructions - Linux**](https://jolla.com/sailfishx-linux-instructions/))
  - Mac computer: chapter 2 in [**Sailfish X instructions - Mac**](https://jolla.com/sailfishx-macos-instructions/)).
- Force your Xperia to _fastboot mode_:
  - hold Volume Up key down and connect the data-connected USB cable (a charging cable would not work)
  - ensure that the LED at the top of the display area is lit in BLUE colour
 (if not, disconnect the cable, release the key and try again)

- You will need the same version of `hybris-recovery.img `as belongs to the Sailfish OS version of your phone currently. In other words, if you have updated OS version 3.4.0 (say) to your phone, then you should use the hybris-recovery.img of that OS release. To ensure this, download the latest Sailfish OS image from **https://shop.jolla.com/downloads/** (provided that you have updated your phon to the latest).  Unzip the archive and observe the hybris-recovery.img file in it.

- Open the Terminal app on your computer. Proceed to the directory where you have the hybris-recovery.img file.
- The following command will enable the Recovery Mode (the BLUE LED should be lit at this point)

 On Windows:

`fastboot flash boot_a hybris-recovery.img`

`fastboot flash boot_b hybris-recovery.img`

`fastboot reboot`

On Linux or Mac:

`sudo fastboot flash boot_a hybris-recovery.img`

`sudo fastboot flash boot_b hybris-recovery.img`

`sudo fastboot reboot`

![](Flashing%20and%20booting%20Xperia%2010%20II%20to%20RecoveryMode.png)

After this, there should not be any BLUE light on your Xperia. Instead, the following text should appear (in a really tiny font) at the top of Xperia display :

_&quot;RECOVERY:  Connect USB cable and open telnet to address 10.42.66.66&quot;_

If you have

- a Windows computer go to chapter 2.2
- a Mac computer go to chapter 2.3
- a Linux computer go to chapter 2.4

### **2.2 Preparing your Windows computer for Recovery Mode**

Do the following to install the &quot;_RNDIS drivers_&quot; and the terminal application properly. If you have used Recovery mode before and installed RNDIS drivers then they _might_ still be okay. If you cannot set up a _telnet_ connection later on, then it is best to check the drivers.

1. Connect your Xperia (which is now in the Recovery Mode after running the steps of chapter 2.1) with an USB cable to your computer. While doing this do not press any buttons of Xperia - simply connect the cable.

 2. Launch Windows Device Manager

- Windows 7:  Open Start Menu and right click on &quot;Computer&quot;. Select &quot;Manage&quot;.
- Windows 10:  Open Start Menu and type &quot;device manager&quot;. You should see Device Manager in the search list now. Alternatively, right click on Windows Start menu and find Device Manager in the list (see picture below).

![](RackMultipart20210511-4-dt6su1_html_f39cdb5bb50eae18.png)

3. Left click on Device Manager and find the Device &quot;_RNDIS_&quot; under &quot;_Other Devices_&quot;, equipped with a  small triangle.  If you do not see it listed, then ensure that you have the item &quot;_Remote NDIS compatible device_&quot; under &quot;_Network adapters_&quot; (this implies that the driver should be ok in your computer).

NOTE: The fastboot device &quot;_sa0114_&quot; of Sony must not appear in the listing of Windows Device Manager at this point any more.

![](RackMultipart20210511-4-dt6su1_html_479e217562d268ec.png)

4. Right click on that device and select Update Driver Software.

![](RackMultipart20210511-4-dt6su1_html_7e944357a325ddd0.png)

5. When the window pops up (Windows 7 and 8 and 10) select &quot;Browse My Computer&quot; for driver software, then on the next screen, click on the bottom that says &quot;Let me pick from a list of drivers on my computer&quot;.

 6. Next you will be asked for the device type. Here you go down to **Network Adapters** – click on it. Select &quot;Next&quot;, then.

 7. Then when it asks you to select manufacturer:

- Windows 7: select &quot;_Microsoft Corporation_&quot;  (do not select &quot;Microsoft&quot;)
- Windows 8 and 10: select &quot;_Microsoft_&quot;

8. Then select &quot;_Remote NDIS Compatible Device_&quot;.

![](RackMultipart20210511-4-dt6su1_html_45a3313d144f39e5.png)

 9. Select &quot;Next&quot;. It will say it is not safe, etc. Ignore this. Proceed to install it. Windows should show a message about successful update. Close it. &quot;_RNDIS_&quot; should appear now below Network adapters.

 10. Next install a Terminal application and enable Telnet. There are two options (in case of Windows 10):

a) Install Putty. Download it from [**www.putty.org**](http://www.putty.org/) \&gt; &quot;_Download PuTTY_&quot; which currently points to [**http://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html**](http://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) **.** Select &quot;_putty.exe_&quot; under &quot;_Alternative binary files_&quot; (make sure you take either the 32-bit or the 64-bit version, depending on your Windows architecture).
b) In case of Windows 10 it is possible to enable the actual Telnet (instead of installing Putty) and run it from the default CMD terminal of Windows (or from PowerShell). This can be done in &quot;Control panel \&gt; Programs \&gt; Programs and Features&quot; by clicking at &quot;T_urn Windows features on or off_&quot; (visible on the left) and then setting the check mark for &quot;_Telnet client_&quot; in the list. Click OK to confirm. Done.

 11. Launch either a) the Putty application or b) the CMD terminal on the PC. Take a) or b) below.

a) On the first screen of Putty select **Telnet** as the Connection type (default is SSH) and then enter and set Host Name (IP address) to **10.42.66.66**. See the picture below. Click Open.

b) In the CMD terminal type &quot;`telnet 10.42.66.66`&quot;  (without the quotes).

![](RackMultipart20210511-4-dt6su1_html_57dabc49b722fc7b.png)

12. You should now see the black Recovery Mode menu on your computer screen (picture below):

![](RackMultipart20210511-4-dt6su1_html_8c29c13b8d18a863.png)

This signifies that you are ready to perform a fix by using Recovery Mode.

You are now ready to move to [**Chapter 3 Fixing your device with Recovery Mode**](https://jolla.zendesk.com/hc/en-us/articles/204709607#3)

### **2.3 Preparing your Mac computer for Recovery Mode**

To run the Recovery Mode on a Mac computer, you need to download the _HoRNDIS driver_ but all other software is already on your computer. You must use version 9 (or later) of HoRNDIS driver.

Citation of proof of [https://joshuawise.com/horndis:](https://joshuawise.com/horndis:)
_&quot;Versions 10.11 and newer of Mac OS X have a rewritten USB stack that is substantially less compatible than that in 10.10 and below. HoRNDIS 9.0 has been rewritten to support MacOS 10.11 and above (El Capitan, Sierra, High Sierra and Mojave); for those versions of MacOS, please try the latest version of HoRNDIS!&quot;_

1. Browse to [www.joshuawise.com/horndis](http://joshuawise.com/horndis)

2. Download and install the latest version of the HoRNDIS driver.

3. After installing the driver you may be prompted to perform a system restart and receive a notification about a &quot;Kernel extension not from an identified developer&quot;: ![](RackMultipart20210511-4-dt6su1_html_52488579cff5d560.png)

Please click OK on the pop-up and restart your computer if you are unsure should you do so or not.

4. Once the driver is installed, attach your Jolla to your Mac. (Note: Jolla must be in &quot;Recovery Mode&quot; before attaching the cable, see [**chapter 2.1**](https://jolla.zendesk.com/hc/en-us/articles/202208763#21))

5. Next you need to locate the Terminal application. To do so:

5a Open Finder
 5b Click the tab &quot;Applications&quot; and open &quot;Utilities&quot;
 ![](RackMultipart20210511-4-dt6su1_html_44fd0e0c2e3d36fd.png)

5c Double-click the Terminal icon to launch it.

![](RackMultipart20210511-4-dt6su1_html_326c2b458128ef18.png)

6. Once Terminal is open, select Shell \&gt; &quot;New Remote Connection...&quot;
 ![](RackMultipart20210511-4-dt6su1_html_4bbcde865ee36891.png)

7. Click on &quot;Remote Login (telnet)&quot; and then the + -icon to add a server.

![](RackMultipart20210511-4-dt6su1_html_f93e2d844e6d4f89.png)

8. Type in the address: 10.42.66.66 and press &quot;OK&quot;.

![](RackMultipart20210511-4-dt6su1_html_223ad52fc29e39e0.png)

9. You should now be in Recovery Mode, with the Recovery Mode menu visible on your computer screen:

![](RackMultipart20210511-4-dt6su1_html_8c29c13b8d18a863.png)

You are now ready to move to [**Chapter 3 Fixing your device with Recovery Mode**](https://jolla.zendesk.com/hc/en-us/articles/204709607#3)



### **2.4 Preparing your Linux computer for Recovery Mode**

It is likely that you won&#39;t need to download any additional software to use Recovery Mode. Below we&#39;ve used Ubuntu.

1.) Connect your Jolla to your PC. You will likely see a notification relating to a disconnect/connect and Ethernet/Wired connection:

![](RackMultipart20210511-4-dt6su1_html_fec49b7bf2f15d58.png)

2.) Open the Terminal application

3.) Type into the Terminal:

**telnet 10.42.66.66**

4.) You should now see the Recovery Mode menu:

![](RackMultipart20210511-4-dt6su1_html_8c29c13b8d18a863.png)

You are now ready to move to [**Chapter 3 Fixing your device with Recovery Mode**](https://jolla.zendesk.com/hc/en-us/articles/204709607#3)



## **3 Fixing your device with Recovery Mode**

### **3.1 Resetting phone to factory settings in Recovery Mode**

NOTE: this option deletes **ALL** data from your device. Resetting to factory settings does not affect data on the SD (memory card) and SIM cards, however.

1. Prepare your PC and device for Recovery Mode (as described in [**Chapter 2**](https://jolla.zendesk.com/hc/en-us/articles/360002996893#2)), until you see the Recovery Menu:

![](RackMultipart20210511-4-dt6su1_html_953aa18805fbd560.png)

2. In the Recovery Mode menu take option #1 &quot;_Reset device to factory state_&quot;

**Note:** If your terminal application suddenly disappears when attempting to run this function, simply connect to Recovery Mode again, and go straight to performing the Device Reset. You may have to repeat this a number of times.

3. Give the process some time to run and follow on-screen instructions.

When the process has completed, please refer to [chapter 3.4](https://jolla.zendesk.com/hc/en-us/articles/360002996893#34) to correctly revert your phone from Recovery Mode back to normal state.

### **3.2 Releasing Xperia from &quot;Permanent lock&quot;**

This requires that you know the correct security code!

In some circumstances it may happen that the allowed maximum number of unlock attempts of the device lock gets exceeded, resulting in &quot;Maximum attempts used. Device is permanently locked&quot;. The following procedure may help in unlocking the device:

- Take option &quot;3) Shell&quot; in the Recovery menu
- Type the following two commands.  In the latter command **replace &quot;12345&quot;** with your correct security code!  These commands work with Sailfish OS version 2.2.0.29, at least.

`
chroot /rootfs
/usr/lib/qt5/plugins/devicelock/encsfa-fpd --check-code 12345
`

-  Type exit to escape the Shell.



### **3.3 Running file system check**

It is possible to have the file system of your Xperia checked by selecting option #4 in the Recovery menu. This utility will try to fix problems if possible, too.

Please type the security code of your Xperia when requested.

The following excerpt shows the output from an Xperia XA2:

`
  Type the number of the desired action and press [Enter]:
  4
  /dev/mmcblk0rpmb: read failed after 0 of 4096 at 0: Input/output error
  /dev/mmcblk0rpmb: read failed after 0 of 4096 at 4128768: Input/output error
  /dev/mmcblk0rpmb: read failed after 0 of 4096 at 4186112: Input/output error
  /dev/mmcblk0rpmb: read failed after 0 of 4096 at 4096: Input/output error
  2 logical volume(s) in volume group "sailfish" now active
  e2fsck 1.45.4 (23-Sep-2019)
  Pass 1: Checking inodes, blocks, and sizes
  Pass 2: Checking directory structure
  Pass 3: Checking directory connectivity
  Pass 4: Checking reference counts
  Pass 5: Checking group summary information
  root: 24319/153600 files (0.5% non-contiguous), 334332/640000 blocks
  Opening encrypted filesystem, you will be prompted for your security code.
  Enter passphrase for /dev/sailfish/home:

  e2fsck 1.45.4 (23-Sep-2019)
  Pass 1: Checking inodes, blocks, and sizes
  Pass 2: Checking directory structure
  Pass 3: Checking directory connectivity
  Pass 4: Checking reference counts
  Pass 5: Checking group summary information
  /dev/mapper/luks-home: 3627/1150560 files (2.1% non-contiguous), 428882/4601344
  blocks
  /dev/mmcblk0rpmb: read failed after 0 of 4096 at 0: Input/output error
  0 logical volume(s) in volume group "sailfish" now active
  Done

Press [Enter] to return to recovery menu...
`



### **3.4 Reverting phone back to the normal state**

It is crucial to follow the below steps to successfully revert your phone from Recovery Mode back to normal state:

 1. Select option 6 &#39;Exit&#39; in the Recovery Mode menu.

2. Disconnect the USB cable from the phone.

3. Press Vol Up key down, keep it pressed and then also press the Power key. When you feel the vibrator play, release Power key.
  - ensure that the LED at the top of the display area is lit in BLUE colour
 (if not, disconnect the cable, release the key and try again)

4. **It is mandatory** to obtain the same version of `hybris-boot.img` that belongs to the Sailfish OS version of your phone currently. In other words, if you have updated OS version 4.1.0 (say) to your phone, then you should use the hybris-boot.img of that OS release. To ensure this, download the latest Sailfish OS image from **https://shop.jolla.com/downloads/** (provided that you have updated your phone to the latest).  Unzip the archive and observe the hybris-boot.img file in it.

- Open the Terminal app on your computer. Proceed to the directory where you have the hybris-boot.img file.
- The following command will restore the boot partition (the BLUE LED should be lit at this point)

 On Windows:

`fastboot flash boot_a hybris-boot.img`

`fastboot flash boot_b hybris-boot.img`

`fastboot reboot`

On Linux or Mac:

`sudo fastboot flash boot_a hybris-boot.img`

`sudo fastboot flash boot_b hybris-boot.img`

`sudo fastboot reboot`

![](Restoring%20Xperia%2010%20II%20boot%20partition.png)

5. After reboot, your phone will be back to the normal state.

Please read this general [**article about factory reset**](https://jolla.zendesk.com/hc/en-us/articles/201890427). In particular, read what is recommended after the factory reset, as explained in chapter &quot;_First actions after the reset&quot;_

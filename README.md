# WICED for MXCHIP Wireless Modules
*Supports EMW3162, EMW3165 and EMW3166*

*Use sales@mxchip.com to contact MXCHIP*

## Using Method
### Preparations
* Download WICED-SDK-5.0.1 in `WICED-WIFI` plate of www.broadcom.com . First you need to register to be a member of their website **with what Broadcom calls a "corporate" e-mail address, so you can't use GMail, Outlook.com or other such e-mail addresses**.
* Download all files from the current repository to your local directory.
* Use the file in folder Addtion instead of `wwd_SDIO.c` in WICED-SDK-5.0.1

### Using Git and Apply Patch file
* Create a git repository for WICED-SDK-5.0.1. Note: you must complete the local submission of the repository in your computer. 
* In this repository, you need run `git apply mxchip_for_WICED-SDK-5.0.1_patch.patch` with git command line or graphical git command. This will decompress and patch WICED SDK.
* As a result,you will find in the path `WICED-SDK-5.0.1\platforms`，there are 3 folders added which are EMW3162, EMW3165 and EMW3166.

### Or Replace target files manually
* Add the file `EMW3162`,`EMW3165`,`EMW3166` in patchs directory to the WICED-SDK-5.0.1 directory `WICED-SDK\platforms`.
* Replace the same files in the `WICED-SDK\tools\OpenOCD` folder with the file in the `patchs\OpenOCD` folder. 

### Then
* Enter the WICED-SDK-5.0.1 SDK directory with the command: `cd WICED-SDK-5.0.1`
* Test flashing an application to the module. In SDK directory, you need run something like `./make EMW<module no>-<app-dir>.<app-name> download run JTAG=<jtag-adapter>` to compile and flash.The followings are examples for EMW3162, EMW3165 and EMW3166.

For EMW3162, using stlink-v2 for flashing, using the application *scan* from the *snip* directory, you should run command like this:
`./make EMW3162-snip.scan download run JTAG=stlink-v2`

For EMW3165, using stlink-v2 for flashing, using the application *scan* from the *snip* directory, you should run command like this:
`./make EMW3165-snip.scan download download_apps run JTAG=stlink-v2`

For EMW3166, using stlink-v2 for flashing, using the application *scan* from the *snip* directory, you should run command like this:
`./make EMW3166-snip.scan download run JTAG=stlink-v2`

You may need to reset modules after flashing process while using st-link-v2.

* If the above steps are successful, you should be able to see log information from debug UART and see the list of Wi-Fi hot spots around.
* From now on，you can start playing around. WICED comes with loads of sample application, so, look around, hack around and make stuff happen.
* Please contact us if you encounter any issues while getting started and running.

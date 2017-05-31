# Install xpenology 6.x

Guide to install xpenology 6.x

### Requirements
- 4GB USB stick
- Make sure harddrives are plugged in direct succession starting from the 1st SATA port. 

### Download:
- [Official DSM 6.0.2](https://usdl.synology.com/download/DSM/release/6.0.2/8451/DSM_DS3615xs_8451.pat)
- [Jun's v1.01 loader](https://mega.nz/#F!BtFQ2DgC!JgomNP3X8V9EuwxL4TXbng!k5NxiIjI) and unzip it.
- [Synology Assistant](https://global.download.synology.com/download/Tools/Assistant/6.1-15030/Windows/synology-assistant-6.1-15030.exe)

# Install via Windows

### Download
- [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/)
- Optional [Extra.lzma](https://mega.nz/#!HERm2ITI!0-eZDuY9pJzSeesON1O9N49QXat8EhvH1b9JtE5KdJo) ramdisk. For network detection or unrecognised HDD controllers. 

### Preparation: VID/PID 
- Mount the USB stick
- Open "Device Manager"
- Find the USB stick
- Right click, select "Properties"
- Select the "Data"-tab and, if necessary, choose from the drop-down list line “Device Instance Id”
- Find the VID_xxxx and PID_xxxx numbers
- Note down the numbers: VID (Vendor ID) will become 0x<number>, PID (Product ID) will become 0x<number>

### Preparation: NIC Mac address
- Determine the mac address (using ifconfig or BIOS) of the xpenology host. Note down the mac address.

### Preparation: Generate serial number
- [Generate a serial number](https://xpenology.github.io/serial_generator/serial_generator_new.html)
- Select "DS3615xs", Generate. Note down the serial.

### Preparation: write image to USB stick
- Insert the USB in the Windows machine
- Open Win32 Disk imager
- Select the "synoboot.img" and write the image.

### Installation
- Insert the USB stick into your new Xpenology host; make sure the USB stick is the first boot device (adjust in BIOS)
- After the BIOS loaded, Jun's loader will only be shown for 1 second: quickly enter `c`.
- GRUB commandline will be shown, enter:

- `vid 0x<number from previous step>`
- `pid 0x<number from previous step>`
- `mac <mac address from previous step>`
- `sn <serial number from previous step>`

- Press `esc` to return to the boot menu

- Choose the first option: `DS3615xs 6.02 Baremetal with Jun's Mod v1.01` and enter
- Xpenology will start up
- Return to your windows host and launch Synology Assistant
- Wait for it to find your Xpenology host (max. 1 minute)
- Choose install (when it is a new host) or migrate to migrate a previous installation. 
- Next you will need to provide DSM 6.0.2 (DSM_DS3615xs_8451.pat)
- Follow the instructions and enjoy!







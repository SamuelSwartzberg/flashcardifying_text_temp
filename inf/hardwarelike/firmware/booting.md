# booting

Booting comes from bootstrap load, which itself comes from the idea of pulling yourself up by your bootstraps.
Booting is initializing the computer.
The difficulty of booting is how do you get the computer into a state where it can execute stuff without being able to execute stuff.
has ended when the OS has reached a certain state.
When the user presses the power button, the computer, and especially the CPU gets power, and executes a hardcoded JUMP fo a place in ROM (or a specific place in normal secondary memory) where the BIOS/UEFI sits (though some non-x86 ISAs may do it differently)
All x86 processors start in real mode, which has the features the intel 8086 had, with 20 bit addresses addressing memory non-virtually - this allows for backwards compatibility.

## BIOS/UEFI

UEFI  Unified Extensible Firmware Interface
BIOS  Basic Input/Output System
The BIOS/UEFI comes preinstalled.
The BIOS stores its setting in nonvolatile BIOS Memory (also inaccurately called CMOS).
One of the more important thing stored in nonvolatile bios memory is boot device priority.
UEFI stores its settings in NVRAM.
Once the BIOS/UEFI is loaded, it typically performs a POST
POST = power-on self-test
POST tests for and initializes connected peripherals.
after BIOS/UEFI are finished, they load the first-stage boot loader.
BIOS loads the first-stage boot loader by looking for the boot sector on the boot device, from then on BIOS is no longer involved in booting.
BIOS is a simple de-facto standard, UEFI is a far more complex actual standard.
UEFI loads the boot loader directly, without using a boot sector.
UEFI has largely replaced BIOS as of 2020.
UEFI is controlled by a large set of industry stakeholders known as teh UEFI forum.
CSM (UEFI context)  Compatibility Support Mode
CSM is the mode of UEFI that makes it similar to BIOS by loading MBR or something from the first-stage boot loader.

to manipulate the UEFI boot manager from linux, use the command efibootmgr
-o/--bootorder|change the boot order

### SMBIOS

DMI  Desktop Management Interface
The original common inteface for managing components of a computer was teh DMI, but it was end-of-lifed in 2005
SMBIOS  System Management BIOS
Originally, the SMBIOS interacted with the DMi
The SMBIOS provides an interface for accessing BIOS/hardware info.
CLI command for interacting with SMBIOS (formerly with the DMI): dmidecode

## boot loader

MBR  Master boot record
The boot sector is typically one sector large
If boot sectors are still used, what sits in them is the first-stage boot loader.
Boot sectors were/are usually in the beginning of the drive
The MBR is 512 byte large, which used to be the size of the boot sector into which the MBR needed to fit.
The main purpose of the first-stage boot loader is to load the second-stage bootloader.
MBR consists both of a first-stage bootloader and a partitioning table.
THe second-stage boot loader, perhaps after some user choosing, loads the kernel.
When using GRUB, all the boot sector contains is a pointer to the next boot stage.
When using GRUB, the boot menu that allows you to choose the os is loaded in the second stage of the bootloader.
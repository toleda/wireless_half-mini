![alt text](https://github.com/toleda/wireless_half-mini/blob/master/wifi.jpeg)
# wireless_half-mini
**OS X Airport Half Mini (WiFi and Bluetooth)**

**Updates**

1. 10/26/16 - 10.12 Support, add
	1. 	config-bcm94352-120.plist
2. 10/7/15 - toledaARPT deprecated
2. 7/23/15 - 10.11 Update, adds
	1. wireless-bcm94352-110.command  
	2. config-bcm94352-110.plist  
3. 7/1/2015 - 10.10.4 Update, adds
	1. wireless-bcm94352-100.command, supports all 10.10 versions  
4. 5/19/15 - 10.10.3 Update: adds
	1. wireless-bcm94352-100-v3.0.command  
	2. config-bcm94352-103.plist  
	3. Country Code support, credit: Sebinouse  
	4. Deprecated Folder. Removed Country Code/XT support    
5. 2/12/15 - 10.10.2 Update; adds
	1. BCM94360HMB
	2. wireless bcm94352-100-v2.0.command
	3. config-bcm94352-102.plist, wireless-bcm94352-100-patch.command deprecated  
6. 12/9/14 - New Broadcomm Bluetooth 4.0 solution, see BCM94352 BT4  
7. 11/19/14 - GYMLE BT4LE/Handoff  
8. 11/16/14 - BCM94352/US-FCC patch, Credit: webcivilian  
9. 11/12/14 - Yosemite Release/BCM94352 5GHz/Handoff  

Airport working OOB on Mavericks with Broadcom BCM94360/BCM94331/BCM943224 and Atheros AR9280   OS X reports as Airport Extreme; Wake on Wireless and AirDrop supported.  Newer Broadcom WiFi cards no longer require rebranding to work in OS X.

BCM943224 HMS, BCM943225 HMB and BCM94352 HMB  PCIe Half Mini versions tested.  AR9280, AR9285 and AR9287 PCIe Half Mini versions tested.   Mini PCIe versions and Mini PCIe to PCIe versions work; BT 4.0 requires USB motherboard connector. 

**Native Airport Half Mini cards**

1. BCM94360HMB - 2.4/5 GHz, ac+abgn, 3 Stream, 1300 Mbs
2. BCM94360CD - 2.4/5 GHz, ac+abgn, 3 Stream, 1300 Mbs  (PCIe x1, not HM)
3. BCM94331CD - 2.4/5 GHz, abgn, 3 stream, 450 Mbs + BT (4.0) 10.10+/Whitelist
4. BCM943224 HMS/HMB - 2.4/5, GHz abgn, 2 stream, 150/300 Mbs 10.10+/Whitelist
5. AR9280 - 2.4/5 GHz, abgn, 2 Stream, 300 Mbs
6. AR9380 - 2.4/5 GHz, abgn, 3 Stream, 450 Mbs

**Non-Native Airport Half Mini cards**  
See [Guide] airport half mini details.pdf

1. BCM94352 HMB - 2.4/5 GHz, ac+abgn, 2 stream, 867 Mbs + BT (4.0)
2. BCM943225 HMS - 2.4 GHz, bgn, 2 stream, 108/150 Mbs
3. BCM943225 HMB - 2.4 GHz, bgn, 2 stream, 108/150 Mbs + BT (3.0)
4. AR9285 - 2.4 GHz, abgn, 1 stream, 54/75 Mbs
5. AR9287 - 2.4 GHz, abgn, 2 stream, 108/150 Mbs

**WiFi + BT**

1. BCM943352 HMB/AzureWave AW-CE123H supports both Airport and Bluetooth 4.0
2. BCM943225 HMB supports both Airport and Bluetooth 3.0

**Airport Injection Methods/Enable WiFi**  
Select one method

1. kext enabler, see FakePCIID for BCM94352
	1. README [FakePCIID -- RehabMan](https://github.com/RehabMan/OS-X-Fake-PCI-ID)
	2. Download [FakePCIID -- RehabMan](https://bitbucket.org/RehabMan/os-x-fake-pci-id/downloads)
2.	kext edit/Info.plist, see [Guide] airport_pcie-hm_plist_edits.pdf above
3.	dsdt edits, [Guide] airport_pcie-hm_dsdt_edits.pdf above
4.	ssdt enabler, see ssdt_arpt folder above
5.	Clover/config.plist/ (Select 1/i or 2/ii, not both)
	1.	ACPI/DSDT/Fixes (supported device_ids)
		1.	AddDTGP_0001/YESFixAirport_4000/YES
		2.	FixAirport_4000/YES
	2.	Devices/FakeID/0x0 (supported device_ids) 

**BCM94352 Country Code**  
Select 1 or 2, not both

1. ROW [WiFi Country Code](http://www.tonymacx86.com/network/104850-guide-airport-pcie-half-mini-v2-117.html#post1027194) Credit: Sebinouse
	1. wireless_bcm94352...command
		1. CC prompt
	2. config-bcm94352...plist
		1. edit 5GHz-US/Replace/55 53 (US) to xx xx (CC)
		2. [ASCII/Hex/Base64](http://www.asciitohex.com)

**BCM94352 5 GHz/Handoff Patch (10.11+)**  
Credit: Dokterdok, the-darkvoid, Sebinouse  
Select 1 or 2, not both

1. Kext/binary patch
   1. Download [wireless_bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/wireless_bcm94352-110-v4.0.command.zip) (select View Raw)
   2. Double click Downloads/wireless_bcm94352-...command
2. Clover/kext patch
   1. Download [config-bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/config-bcm94352-110.plist.zip) (select View Raw)
	1. Paste 3 Patches to config.plist/KernelAndKextPatches/KextsToPatch

**BCM94352 5 GHz/Handoff Patch (10.10+)**  
Credit: Dokterdok, the-darkvoid, Sebinouse  
Select 1 or 2, not both

1. Kext/binary patch
   1. Download [wireless_bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/wireless_bcm94352-100.command.zip) (select View Raw)
   2. Double click Downloads/wireless_bcm94352-...command
2. Clover/kext patch
   1. Download [config-bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/config-bcm94352-103.plist.zip) (select View Raw)
	1. Paste 3 Patches to config.plist/KernelAndKextPatches/KextsToPatch

**BCM94352 5 GHz Patch (10.9+)**  
Credit: Skvo  
Select 1 or 2, not both

1. Kext/binary patch
	1. Download [wireless_bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/wireless_bcm94352-90_patch.command.zip) (select View Raw)
   2. Double click Downloads/wireless_bcm94352-...command
   3. See Terminal Saved Output. . . (above)
2. Clover/kext patch
   1. Download [config-bcm94352-...](https://github.com/toleda/wireless_half-mini/blob/master/config-bcm94352-103.plist.zip) (select View Raw)
   2. Add 3 Patches to config.plist/KernelAndKextPatches/KextsToPatch

**Bluetooth 4LE (10.11+)**

1.	10.11 USB Issues/no BT
	1. Fix USB problem
2.	BT injection - RehabMan/OS-X-BrcmPatchRAM (2 kexts required)
	1.	REAMDME [BrcmPatchRAM -- RehabMan](https://github.com/RehabMan/OS-X-BrcmPatchRAM)
	2. Download [BrcmPatchRAM -- RehabMan](https://bitbucket.org/RehabMan/os-x-brcmpatchram/downloads)
	3. Install 2 kexts
		1.	BrcmFirmwareRepo.kext
		2.	BrcmPatchRAM2.kext
3.	Installation (a or b, not both)
	1.	Clover/Chameleon - use kext installer
		1.	System/Library/Extensions/
		2.	Library/Extensions/
4.	Working
	1.	Asus BCM94352 (0b05/17cf)
	2.	Azurewave CE-123H (13d3/3404)

**Bluetooth 4LE/4/3 (10.10+. 10.9+)**

1. REAMDME [BrcmPatchRAM -- RehabMan](https://github.com/RehabMan/OS-X-BrcmPatchRAM)
2. Download [BrcmPatchRAM -- RehabMan](https://bitbucket.org/RehabMan/os-x-brcmpatchram/downloads)
3.	BrcmPatchRAM.kext Installation (Select one method)
	1.	Clover/Chameleon - System/Library/Extensions/
		1.	use kext installer
	2.	Clover - EFI/CLOVER/kexts/10.10 or /10.9
4.	Working
	1.	Asus BCM94352 (0b05/17cf)
	2.	Azurewave CE-123H (13d3/3404

**Requirement** (+ all)

1.  OS X Versions (+ all)
    1.  10.11+/El Capitan 
    2.  10.10+/Yosemite
    3.  10.9+/Mavericks
    4.  10.8.5/Mountain Lion  
    Solution does not work, 10.8.4 or earlier
2. Boot Flags/Boot failure may result if ignored
	1. 10.11+/Disable SIP/set, restart, install, enable SIP, restart
		1. CLOVER/config.plist/RtVariables/
			1. BooterConfig/0x28
			2. CsrActiveConfig/0x3
		2. Chameleon - Extra/org.chameleon.Boot.plist
			1. CsrActiveConfig=3
	2. 10.10+/Allow unsigned kexts/set, restart, install
		1. Clover/config.plist/
			1. Boot/Arguments/kext-dev-mode=1
		2. Chameleon/Extra/org.chameleon.Boot.plist/
			1. Kernel Flags/kext-dev-mode=1

**Installation/Configuration/Troubleshooting**  
[Guide] airport_half-mini_details.pdf.zip (above)

**Tools**

1. [IOReg_v2.1](https://github.com/toleda/audio_ALCInjection/blob/master/IORegistryExplorer_v2.1.zip) (select View Raw)
2. [DPCIManger](http://sourceforge.net/projects/dpcimanager/)  
3. [MaciASL](http://sourceforge.net/projects/maciasl/)
4. Property List Editors -
	1. [Xcode](https://developer.apple.com/xcode/)  
	2. Property List Editor, PlistEdit Pro, TextEdit, etc.
	3. TextEdit, TextWrangler (last resort)
5. [Clover Configurator](http://www.osx86.net/files/file/49-clover-configurator/)
6. [Clover Wiki](http://clover-wiki.zetam.org/Home)

**Problem Reporting** (attach requested information)

1. Description of wireless problem
2. OS X version/motherboard model/BIOS version/processor/graphics
3. Procedure/Guide used
4. Copy of IOReg - IOReg_v2.1/File/Save a Copy As…, verify file (Tools 1.)
5.	Screenshots:
	1. DPCIManager/Status (Tools 2.)
	2. System Information/Hardware/Network/WiFi
	3. System Information/Hardware/Bluetooth
	4. System Information/Hardware/USB (Select Bluetooth 	device)
6.	DPCIManager/Misc/Boot Log
7.	MaciASL/File/Export Tableset As... (Tools 3.)
8.	Terminal/Shell/File/Export Text As. . . /wireless_bcm...command
9.	Chameleon
	1.	Extra/org.chameleon.Boot.plist
	2.	DPCIManager/Misc/Boot Log
	3.	Extra/dsdt.aml (if installed)
	4.	Extra/ssdt.aml (if installed)
10.	Clover
	1.	EFI/CLOVER/config.plist
	2.	DPCIManager/Misc/Boot Log
	3.	EFI/CLOVER/ACPI/Patched/dsdt.aml (if installed)
	4.	EFI/CLOVER/ACPI/Patched/ssdt.aml (if installed)
11.	Post to:
	1.	[Airport - InsanelyMac.com](http://www.insanelymac.com/forum/topic/292542-airport-pcie-half-mini/)
	2. [Airport - tonymacx86.com](http://www.tonymacx86.com/network/104850-guide-airport-pcie-half-mini-v2.html)

Credit  
THe KiNG   
Andy Vandijck  
PikeRAlpha  
Skvo  
Dokterdok  
the-darkvoid  
Sebinouse  

toleda
https://github.com/toleda/airport_half_mini

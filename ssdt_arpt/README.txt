ssdt_arpt
============
MacOS Airport Half Mini

An ssdt_arpt/94352 enables native Airport with non-native Broadcom WiFi PCIe Half Mini cards on macOS 10.10 and newer. This method avoids dsdt and kext edits and is immune to Software Updates and BIOS revisions. 

Requirements
1. 10.10 or newer
2. AMI 6/7/8/9/100/200 Series UEFI
3. Airport Wifi card at: IOReg/RP0x/PSXS@0/vendor-id 
3a. <e4 14 00 00> (BCM)

ssdt_arpt/94352
1. airport_ssdt-ami..-bcm43xx_v1, supports
1a. BCM94352 HMB - 2.4/5 GHz, ac+abgn, 2 stream, 867 Mbs + BT (4.0)

Downloads (select one*)
1. ssdt_arpt-rp02-bcm4352.zip/View Raw/Save as .zip
2. ssdt_arpt-rp03-bcm4352.zip/View Raw/Save as .zip
3. ssdt_arpt-rp04-bcm4352.zip/View Raw/Save as .zip
4. ssdt_arpt-rp05-bcm4352.zip/View Raw/Save as .zip
5. ssdt_arpt-rp06-bcm4352.zip/View Raw/Save as .zip
6. ssdt_arpt-rp07-bcm4352.zip/View Raw/Save as .zip

Tools
1. IORegistryExplorer https://github.com/toleda/audio_ALCInjection/blob/master/IORegistryExplorer_v2.1.zip
2. MaciASL http://sourceforge.net/projects/maciasl/?source=directory
3. DPCIManager http://sourceforge.net/projects/dpcimanager/

Edit airport PCIe Device Name, if necessary (IOReg/RP0x)
1. MaciASL/File/Open/Downloads/airport_ssdt-…
2. Find: Method (_SB.PCI0.RP04.PXSX._DSM, 4, NotSerialized)
3. Edit: RP04 to RP0x (Use value x from IOReg/RP0x)
4. Save

Installation
1. Copy Downloads/ssdt-arpt.. . ./SSDT-ARPT-RP0x-4352.aml to CLOVER/ACPI/patched/
2. Restart

Credit
MasterChef
bcc9 http://www.insanelymac.com/forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/?p=1934889
PikeRAlpha https://pikeralpha.wordpress.com/2013/06/16/intel-hd4600-with-full-resolution/

toleda
https://github.com/toleda/wireless_half-mini

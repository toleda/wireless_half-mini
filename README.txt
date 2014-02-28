wireless_half-mini
============
OS X Airport Half Mini (WiFi and Bluetooth)

Airport working OOB on Mavericks with Broadcom BCM4360  and Atheros AR9280   OS X reports as Airport Extreme; Wake on Wireless and AirDrop supported.  Newer Broadcom WiFi cards no longer require rebranding to work in OS X.

BCM943224 HMS, BCM943225 HMB and BCM94352 HMB  PCIe Half Mini versions tested.  AR9280, AR9285 and AR9287 PCIe Half Mini versions tested.   Mini PCIe versions  and Mini PCIe to PCIe versions expected to work. 

Requirements
1. 10.9 and newer
1. 10.8.5 or newer (This solution does not work in 10.8.4 or earlier) 

Airport Half Mini Guides:
[Guide]_airport_half-mini_details.pdf.zip
[Guide]_airport_half-mini_dsdt_edits.pdf.zip
[Guide]_airport_half-mini_plist_edits.pdf.zip

Native Airport Half Mini cards.
2. BCM4360 - 2.4/5 GHz, ac+abgn, 3 Stream, 1300 Mbs  (PCIe x1, not HM at this time)
3. AR9280 - 2.4/5 GHz, abgn, 2 Stream, 300 Mbs
4. AR9380 - 2.4/5 GHz, abgn, 3 Stream, 450 Mbs

Non-Native Airport Half Mini cards, see [Guide] airport_half_mini_details.pdf
1. BCM943224 HMS - 2.4/5, GHz abgn, 2 stream, 150/300 Mbs
1. BCM943225 HMS - 2.4 GHz, bgn, 2 stream, 108/150 Mbs
2. BCM943225 HMB - 2.4 GHz, bgn, 2 stream, 108/150 Mbs + BT (3.0)
3. BCM94352 HMB - 2.4/5 GHz, ac+abgn, 2 stream, 867 Mbs + BT (4.0)
4. AR9285 - 2.4 GHz, abgn, 1 stream, 54/75 Mbs
5. AR9287 - 2.4 GHz, abgn, 2 stream, 108/150 Mbs

WiFi + BT
1. BCM943352 HMB/AzureWave AW-CE123H supports both Airport and Bluetooth 4.0
Note: The Asus Superfast 802.11ac (Z87 Pro & Deluxe motherboards) is BCM4352
2. BCM943225 HMB supports both Airport and Bluetooth 3.0
3. For any working WiFi without BT; 4.0, wake, low energy, native - suggest:
http://www.gmyle.com/products/micro-usb-bluetooth-4-0-dongle-dual-mode-w-low-energy-technology-wireless-adapter-broadcom-bcm20702-chipset-x10

BCM94352 5 GHz Patch (10.9 and newer) - Credit: Skvo
1. Download (View Raw) wireless_half-mini-brcm4360-90_patch.command.zip

Airport Injection Methods
1. kext enabler, see airport_kext_enabler/README.txt
2. kext edit/Info.plist, see [Guide] airport_half_mini_plist_edits.pdf
3. dsdt edits, [Guide] airport_half_mini_dsdt_edits.pdf
4. ssdt enabler, see airport_ssdt_enabler/README.txt

Installation/Configuration/Troubleshooting
[Guide] airport_half-mini_details.pdf.zip

Problem Reporting (include the following information)
1. Description of wireless problem
2. OS X version/motherboard model/BIOS version/processor/graphics
3. Copy of IOReg - IOReg_v2.1/File/Save a Copy As…, verify file (not
   ioreg.txt)
4. Extra/org.chameleon.Boot.plist or EFI/Clover/config.plist
5. Extra/dsdt.aml or EFI/Clover/ACPI/Patched/dsdt.aml (if installed)
6. Extra/dsdt.aml or EFI/Clover/ACPI/Patched/ssdt.aml (if installed)
7. Console/All Messages/kernel bcn/ath messages selected/Save
   Selection As…..
8. WiFi: Screenshot of System Information/Hardware/Network and WiFi
9. Bluetooth: Screenshot of System Information/Hardware/Bluetooth and 
   USB/Bluetooth USB Host Controller
Post to:
1. http://www.tonymacx86.com/network/104850-guide-airport-pcie-half-mini-v2.html
2. http://www.insanelymac.com/forum/topic/292542-airport-pcie-half-mini/

Credit
THe KiNG 
Andy Vandijck
PikeRAlpha
EMlyDinEsH
Skvo

toleda
https://github.com/toleda/airport_half_mini
[Guide] airport_half-mini_details.pdf
[Guide] airport_half-mini_dsdt_edits.pdf
[Guide] airport_half-mini_plist_edits.pdf
README.txt
Files:
ARPTEnablers
Patches

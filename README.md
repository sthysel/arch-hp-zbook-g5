# Arch on HP zbook G5

Notes on installing Arch on the HP Zbook G5.

Arch works fine on the HP Zbook and its accociated dock.

## Base installing

[Follow basic install guide](https://wiki.archlinux.org/index.php/Installation_guide) as usual.

The arch wiki has gained a [dedicated page for the zbook
G5](https://wiki.archlinux.org/index.php/HP_Zbook_Studio_G5) recently, which
notes most everything important for a base install.

## HiDPI

Using the DPI screen and a large HD monitor https://wiki.archlinux.org/index.php/HiDPI


# system notes

## lspci

```
$ lspci

00:00.0 Host bridge: Intel Corporation 8th Gen Core Processor Host Bridge/DRAM Registers (rev 07)
00:01.0 PCI bridge: Intel Corporation Xeon E3-1200 v5/E3-1500 v5/6th Gen Core Processor PCIe Controller (x16) (rev 07)
00:04.0 Signal processing controller: Intel Corporation Xeon E3-1200 v5/E3-1500 v5/6th Gen Core Processor Thermal Subsystem (rev 07)
00:12.0 Signal processing controller: Intel Corporation Cannon Lake PCH Thermal Controller (rev 10)
00:13.0 Serial controller: Intel Corporation Device a37c (rev 10)
00:14.0 USB controller: Intel Corporation Cannon Lake PCH USB 3.1 xHCI Host Controller (rev 10)
00:14.2 RAM memory: Intel Corporation Cannon Lake PCH Shared SRAM (rev 10)
00:14.3 Network controller: Intel Corporation Wireless-AC 9560 [Jefferson Peak] (rev 10)
00:15.0 Serial bus controller [0c80]: Intel Corporation Cannon Lake PCH Serial IO I2C Controller (rev 10)
00:15.1 Serial bus controller [0c80]: Intel Corporation Cannon Lake PCH Serial IO I2C Controller (rev 10)
00:16.0 Communication controller: Intel Corporation Cannon Lake PCH HECI Controller (rev 10)
00:16.3 Serial controller: Intel Corporation Cannon Lake PCH Active Management Technology - SOL (rev 10)
00:17.0 SATA controller: Intel Corporation Cannon Lake Mobile PCH SATA AHCI Controller (rev 10)
00:1c.0 PCI bridge: Intel Corporation Cannon Lake PCH PCI Express Root Port #3 (rev f0)
00:1c.4 PCI bridge: Intel Corporation Cannon Lake PCH PCI Express Root Port #5 (rev f0)
00:1d.0 PCI bridge: Intel Corporation Cannon Lake PCH PCI Express Root Port #9 (rev f0)
00:1f.0 ISA bridge: Intel Corporation Device a30e (rev 10)
00:1f.3 Audio device: Intel Corporation Cannon Lake PCH cAVS (rev 10)
00:1f.4 SMBus: Intel Corporation Cannon Lake PCH SMBus Controller (rev 10)
00:1f.5 Serial bus controller [0c80]: Intel Corporation Cannon Lake PCH SPI Controller (rev 10)
00:1f.6 Ethernet controller: Intel Corporation Ethernet Connection (7) I219-LM (rev 10)
01:00.0 VGA compatible controller: NVIDIA Corporation GP107GLM [Quadro P2000 Mobile] (rev a1)
02:00.0 Unassigned class [ff00]: Realtek Semiconductor Co., Ltd. RTS525A PCI Express Card Reader (rev 01)
04:00.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge 4C 2018] (rev 06)
05:00.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge 4C 2018] (rev 06)
05:01.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge 4C 2018] (rev 06)
05:02.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge 4C 2018] (rev 06)
05:04.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge 4C 2018] (rev 06)
06:00.0 System peripheral: Intel Corporation JHL7540 Thunderbolt 3 NHI [Titan Ridge 4C 2018] (rev 06)
07:00.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge DD 2018] (rev 06)
08:02.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge DD 2018] (rev 06)
08:04.0 PCI bridge: Intel Corporation JHL7540 Thunderbolt 3 Bridge [Titan Ridge DD 2018] (rev 06)
09:00.0 USB controller: Intel Corporation JHL7540 Thunderbolt 3 USB Controller [Titan Ridge 4C 2018] (rev 06)
6f:00.0 Non-Volatile memory controller: Samsung Electronics Co Ltd NVMe SSD Controller SM981/PM981
```

## dmidecode

```
$ sudo dmidecode 


# dmidecode 3.2
Getting SMBIOS data from sysfs.
SMBIOS 3.1 present.
40 structures occupying 2778 bytes.
Table at 0x9B374000.

Handle 0x0000, DMI type 43, 31 bytes
TPM Device
	Vendor ID: IFX
	Specification Version: 2.0	Firmware Revision: 7.63
	Description: SLB9670	Characteristics:
		Family configurable via firmware update
		Family configurable via platform software support
	OEM-specific Information: 0x00000000

Handle 0x0001, DMI type 0, 26 bytes
BIOS Information
	Vendor: HP
	Version: Q70 Ver. 01.04.02
	Release Date: 10/05/2018
	Address: 0xF0000
	Runtime Size: 64 kB
	ROM Size: 32 MB
	Characteristics:
		PCI is supported
		PC Card (PCMCIA) is supported
		BIOS is upgradeable
		BIOS shadowing is allowed
		Boot from CD is supported
		Selectable boot is supported
		EDD is supported
		Print screen service is supported (int 5h)
		8042 keyboard services are supported (int 9h)
		Serial services are supported (int 14h)
		Printer services are supported (int 17h)
		ACPI is supported
		USB legacy is supported
		Smart battery is supported
		BIOS boot specification is supported
		Function key-initiated network boot is supported
		Targeted content distribution is supported
		UEFI is supported
	BIOS Revision: 4.2
	Firmware Revision: 21.48

Handle 0x0002, DMI type 1, 27 bytes
System Information
	Manufacturer: HP
	Product Name: HP ZBook 15 G5
	Version:  
	Serial Number: 5CD8484V89
	UUID: 59107e9d-06a6-9005-abb8-3a8cac2b923e
	Wake-up Type: Power Switch
	SKU Number: 3AX09AV
	Family: 103C_5336AN HP ZBook 15

Handle 0x0003, DMI type 2, 17 bytes
Base Board Information
	Manufacturer: HP
	Product Name: 842A
	Version: KBC Version 15.30.00
	Serial Number: PHMYU018JBJ02F
	Asset Tag:  
	Features:
		Board is a hosting board
	Location In Chassis:  
	Chassis Handle: 0x0000
	Type: Motherboard
	Contained Object Handles: 0

Handle 0x0004, DMI type 3, 24 bytes
Chassis Information
	Manufacturer: HP
	Type: Notebook
	Lock: Not Present
	Version:  
	Serial Number: 5CD8484V89
	Asset Tag: 5CD8484V89
	Boot-up State: Safe
	Power Supply State: Safe
	Thermal State: Safe
	Security Status: None
	OEM Information: 0x00000000
	Height: Unspecified
	Number Of Power Cords: Unspecified
	Contained Elements: 0
	SKU Number: Not Specified

Handle 0x0006, DMI type 13, 22 bytes
BIOS Language Information
	Language Description Format: Abbreviated
	Installable Languages: 14
		enUS
		deDE
		esES
		itIT
		frFR
		jaJA
		ptPT
		daDA
		svSV
		nlBE
		noNO
		fiFI
		zhCN
		zhTW
	Currently Installed Language: enUS

Handle 0x0007, DMI type 16, 23 bytes
Physical Memory Array
	Location: System Board Or Motherboard
	Use: System Memory
	Error Correction Type: None
	Maximum Capacity: 64 GB
	Error Information Handle: Not Provided
	Number Of Devices: 4

Handle 0x000C, DMI type 19, 31 bytes
Memory Array Mapped Address
	Starting Address: 0x00000000000
	Ending Address: 0x00FFFFFFFFF
	Range Size: 64 GB
	Physical Array Handle: 0x0007
	Partition Width: 4

Handle 0x000D, DMI type 221, 26 bytes
HP BIOS iSCSI NIC PCI and MAC Information
	NIC 1: PCI device 01:00.3, MAC address 00:07:00:35:42:00
	NIC 2: PCI device 00:00.2, MAC address 00:00:00:96:00:03

Handle 0x000E, DMI type 221, 26 bytes
HP BIOS iSCSI NIC PCI and MAC Information
	NIC 1: PCI device 01:00.3, MAC address 00:07:00:35:42:00
	NIC 2: PCI device 00:00.2, MAC address 0C:00:00:0A:00:03

Handle 0x000F, DMI type 221, 89 bytes
HP BIOS iSCSI NIC PCI and MAC Information
	NIC 1: PCI device 01:01.4, MAC address 00:07:00:35:42:00
	NIC 2: PCI device 03:00.2, MAC address FF:FF:FF:FF:FF:04
	NIC 3: PCI device ff:00.0, MAC address FF:FF:10:00:05:00
	NIC 4: Not Installed
	NIC 5: Not Installed
	NIC 6: Disabled
	NIC 7: Disabled
	NIC 8: PCI device 0a:00.0, MAC address 00:13:00:00:00:00
	NIC 9: PCI device 00:01.3, MAC address 07:00:00:00:00:0C
	NIC 10: PCI device 06:00.0, MAC address 00:00:00:00:0D:00

Handle 0x0010, DMI type 221, 54 bytes
HP BIOS iSCSI NIC PCI and MAC Information
	NIC 1: PCI device 01:00.7, MAC address 00:07:00:35:42:00
	NIC 2: PCI device 00:00.2, MAC address 00:07:01:47:00:03
	NIC 3: PCI device 07:00.0, MAC address 00:35:42:00:04:05
	NIC 4: Not Installed
	NIC 5: Disabled
	NIC 6: PCI device 07:00.0, MAC address 00:08:00:FF:FF:FF

Handle 0x0011, DMI type 221, 12 bytes
HP BIOS iSCSI NIC PCI and MAC Information
	NIC 1: PCI device 01:00.1, MAC address 00:04:00:00:00:00

Handle 0x0012, DMI type 7, 27 bytes
Cache Information
	Socket Designation: L1 Cache
	Configuration: Enabled, Not Socketed, Level 1
	Operational Mode: Write Back
	Location: Internal
	Installed Size: 384 kB
	Maximum Size: 384 kB
	Supported SRAM Types:
		Synchronous
	Installed SRAM Type: Synchronous
	Speed: Unknown
	Error Correction Type: Parity
	System Type: Unified
	Associativity: 8-way Set-associative

Handle 0x0013, DMI type 7, 27 bytes
Cache Information
	Socket Designation: L2 Cache
	Configuration: Enabled, Not Socketed, Level 2
	Operational Mode: Write Back
	Location: Internal
	Installed Size: 1536 kB
	Maximum Size: 1536 kB
	Supported SRAM Types:
		Synchronous
	Installed SRAM Type: Synchronous
	Speed: Unknown
	Error Correction Type: Single-bit ECC
	System Type: Unified
	Associativity: 4-way Set-associative

Handle 0x0014, DMI type 7, 27 bytes
Cache Information
	Socket Designation: L3 Cache
	Configuration: Enabled, Not Socketed, Level 3
	Operational Mode: Write Back
	Location: Internal
	Installed Size: 12288 kB
	Maximum Size: 12288 kB
	Supported SRAM Types:
		Synchronous
	Installed SRAM Type: Synchronous
	Speed: Unknown
	Error Correction Type: Multi-bit ECC
	System Type: Unified
	Associativity: 16-way Set-associative

Handle 0x0015, DMI type 4, 48 bytes
Processor Information
	Socket Designation: U3E1
	Type: Central Processor
	Family: Xeon
	Manufacturer: Intel(R) Corporation
	ID: EA 06 09 00 FF FB EB BF
	Signature: Type 0, Family 6, Model 158, Stepping 10
	Flags:
		FPU (Floating-point unit on-chip)
		VME (Virtual mode extension)
		DE (Debugging extension)
		PSE (Page size extension)
		TSC (Time stamp counter)
		MSR (Model specific registers)
		PAE (Physical address extension)
		MCE (Machine check exception)
		CX8 (CMPXCHG8 instruction supported)
		APIC (On-chip APIC hardware supported)
		SEP (Fast system call)
		MTRR (Memory type range registers)
		PGE (Page global enable)
		MCA (Machine check architecture)
		CMOV (Conditional move instruction supported)
		PAT (Page attribute table)
		PSE-36 (36-bit page size extension)
		CLFSH (CLFLUSH instruction supported)
		DS (Debug store)
		ACPI (ACPI supported)
		MMX (MMX technology supported)
		FXSR (FXSAVE and FXSTOR instructions supported)
		SSE (Streaming SIMD extensions)
		SSE2 (Streaming SIMD extensions 2)
		SS (Self-snoop)
		HTT (Multi-threading)
		TM (Thermal monitor supported)
		PBE (Pending break enabled)
	Version: Intel(R) Xeon(R) E-2186M  CPU @ 2.90GHz
	Voltage: 0.9 V
	External Clock: 100 MHz
	Max Speed: 4800 MHz
	Current Speed: 2772 MHz
	Status: Populated, Enabled
	Upgrade: Socket BGA1440
	L1 Cache Handle: 0x0012
	L2 Cache Handle: 0x0013
	L3 Cache Handle: 0x0014
	Serial Number: To Be Filled By O.E.M.
	Asset Tag: To Be Filled By O.E.M.
	Part Number: To Be Filled By O.E.M.
	Core Count: 6
	Core Enabled: 6
	Thread Count: 12
	Characteristics:
		64-bit capable
		Multi-Core
		Hardware Thread
		Execute Protection
		Enhanced Virtualization
		Power/Performance Control

Handle 0x0016, DMI type 8, 9 bytes
Port Connector Information
	Internal Reference Designator: Ctrl0Port0
	Internal Connector Type: SAS/SATA Plug Receptacle
	External Reference Designator: SSD1
	External Connector Type: SAS/SATA Plug Receptacle
	Port Type: SATA

Handle 0x0017, DMI type 8, 9 bytes
Port Connector Information
	Internal Reference Designator: Ctrl0Port1
	Internal Connector Type: SAS/SATA Plug Receptacle
	External Reference Designator: HDD1
	External Connector Type: SAS/SATA Plug Receptacle
	Port Type: SATA

Handle 0x0018, DMI type 8, 9 bytes
Port Connector Information
	Internal Reference Designator: Ctrl0Port4
	Internal Connector Type: SAS/SATA Plug Receptacle
	External Reference Designator: SSD2
	External Connector Type: SAS/SATA Plug Receptacle
	Port Type: SATA

Handle 0x0019, DMI type 9, 17 bytes
System Slot Information
	Designation: M2 WLAN/BT
	Type: x1 PCI Express 3 x1
	Current Usage: Available
	Length: Long
	ID: 1
	Characteristics:
		3.3 V is provided
		PME signal is supported
		SMBus signal is supported
	Bus Address: 0000:00:1c.3

Handle 0x001A, DMI type 9, 17 bytes
System Slot Information
	Designation: M2 SSD
	Type: x4 PCI Express 3 x4
	Current Usage: In Use
	Length: Long
	ID: 2
	Characteristics:
		3.3 V is provided
		PME signal is supported
		SMBus signal is supported
	Bus Address: 0000:00:1d.0

Handle 0x001B, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard IGD
	Type: Video
	Status: Enabled
	Type Instance: 1
	Bus Address: 0000:00:02.0

Handle 0x001C, DMI type 130, 20 bytes
OEM-specific Type
	Header and Data:
		82 14 1C 00 24 41 4D 54 01 01 01 01 01 A5 FF 02
		C0 00 01 00

Handle 0x001D, DMI type 131, 64 bytes
OEM-specific Type
	Header and Data:
		83 40 1D 00 35 00 00 00 0C 00 00 00 00 00 0A 00
		F8 00 0E A3 00 00 00 00 09 C0 00 00 00 00 0C 00
		62 04 07 00 00 00 00 00 FE 00 BB 15 00 00 00 00
		00 00 00 00 26 00 00 00 76 50 72 6F 00 00 00 00

Handle 0x001E, DMI type 17, 40 bytes
Memory Device
	Array Handle: 0x0007
	Error Information Handle: Not Provided
	Total Width: 64 bits
	Data Width: 64 bits
	Size: 16384 MB
	Form Factor: SODIMM
	Set: None
	Locator: Top-Slot 1(left)
	Bank Locator: BANK 0
	Type: DDR4
	Type Detail: Synchronous
	Speed: 2667 MT/s
	Manufacturer: Samsung
	Serial Number: 40CC2E87
	Asset Tag:  
	Part Number: M471A2K43DB1-CTD    
	Rank: 2
	Configured Memory Speed: 2400 MT/s
	Minimum Voltage: Unknown
	Maximum Voltage: Unknown
	Configured Voltage: 1.2 V

Handle 0x0009, DMI type 17, 40 bytes
Memory Device
	Array Handle: 0x0007
	Error Information Handle: Not Provided
	Total Width: 64 bits
	Data Width: 64 bits
	Size: 16384 MB
	Form Factor: SODIMM
	Set: None
	Locator: Top-Slot 2(right)
	Bank Locator: BANK 1
	Type: DDR4
	Type Detail: Synchronous
	Speed: 2667 MT/s
	Manufacturer: Samsung
	Serial Number: 40CC3341
	Asset Tag:  
	Part Number: M471A2K43DB1-CTD    
	Rank: 2
	Configured Memory Speed: 2400 MT/s
	Minimum Voltage: Unknown
	Maximum Voltage: Unknown
	Configured Voltage: 1.2 V

Handle 0x000B, DMI type 17, 40 bytes
Memory Device
	Array Handle: 0x0007
	Error Information Handle: Not Provided
	Total Width: 64 bits
	Data Width: 64 bits
	Size: 16384 MB
	Form Factor: SODIMM
	Set: None
	Locator: Bottom-Slot 1(left)
	Bank Locator: BANK 2
	Type: DDR4
	Type Detail: Synchronous
	Speed: 2667 MT/s
	Manufacturer: Samsung
	Serial Number: 40CC3F35
	Asset Tag:  
	Part Number: M471A2K43DB1-CTD    
	Rank: 2
	Configured Memory Speed: 2400 MT/s
	Minimum Voltage: Unknown
	Maximum Voltage: Unknown
	Configured Voltage: 1.2 V

Handle 0x0008, DMI type 17, 40 bytes
Memory Device
	Array Handle: 0x0007
	Error Information Handle: Not Provided
	Total Width: 64 bits
	Data Width: 64 bits
	Size: 16384 MB
	Form Factor: SODIMM
	Set: None
	Locator: Bottom-Slot 2(right)
	Bank Locator: BANK 3
	Type: DDR4
	Type Detail: Synchronous
	Speed: 2667 MT/s
	Manufacturer: Samsung
	Serial Number: 40CC3C31
	Asset Tag:  
	Part Number: M471A2K43DB1-CTD    
	Rank: 2
	Configured Memory Speed: 2400 MT/s
	Minimum Voltage: Unknown
	Maximum Voltage: Unknown
	Configured Voltage: 1.2 V

Handle 0x000A, DMI type 20, 35 bytes
Memory Device Mapped Address
	Starting Address: 0x00000000000
	Ending Address: 0x003FFFFFFFF
	Range Size: 16 GB
	Physical Device Handle: 0x001E
	Memory Array Mapped Address Handle: 0x000C
	Partition Row Position: 1

Handle 0x001F, DMI type 20, 35 bytes
Memory Device Mapped Address
	Starting Address: 0x00400000000
	Ending Address: 0x007FFFFFFFF
	Range Size: 16 GB
	Physical Device Handle: 0x0009
	Memory Array Mapped Address Handle: 0x000C
	Partition Row Position: 1
	Interleave Position: 1

Handle 0x0020, DMI type 20, 35 bytes
Memory Device Mapped Address
	Starting Address: 0x00800000000
	Ending Address: 0x00BFFFFFFFF
	Range Size: 16 GB
	Physical Device Handle: 0x000B
	Memory Array Mapped Address Handle: 0x000C
	Partition Row Position: 1
	Interleaved Data Depth: 1

Handle 0x0021, DMI type 20, 35 bytes
Memory Device Mapped Address
	Starting Address: 0x00C00000000
	Ending Address: 0x00FFFFFFFFF
	Range Size: 16 GB
	Physical Device Handle: 0x0008
	Memory Array Mapped Address Handle: 0x000C
	Partition Row Position: 1
	Interleave Position: 1
	Interleaved Data Depth: 1

Handle 0x0022, DMI type 22, 26 bytes
Portable Battery
	Location: Primary
	Manufacturer: 333-1C-2C-A
	Name: VX04090XL
	Design Capacity: 89990 mWh
	Design Voltage: 15400 mV
	SBDS Version: 1.1
	Maximum Error: Unknown
	SBDS Serial Number: 0796
	SBDS Manufacture Date: 2018-07-09
	SBDS Chemistry: LION
	OEM-specific Information: 0x00000000

Handle 0x0023, DMI type 24, 5 bytes
Hardware Security
	Power-On Password Status: Disabled
	Keyboard Password Status: Disabled
	Administrator Password Status: Disabled
	Front Panel Reset Status: Disabled

Handle 0x0024, DMI type 32, 11 bytes
System Boot Information
	Status: No errors detected

Handle 0x0025, DMI type 11, 5 bytes
OEM Strings
	String 1: FBYTE#3X476J6S6b7B7M7Q7U7W7m7saBaEapaqauawbhcAdUdpdqgdh5hKhZjh.yy;
	String 2: BUILDID#18WWAVBT601#SABG#DABG;
	String 3: EDK2_1
	String 4: Buff=2
	String 5: HRDWFEATS=VMCSSHAD:1;VTX:1;VTD:1;SGX:0;NONHPBATDET:1

Handle 0x0005, DMI type 14, 8 bytes
Group Associations
	Name: $MEI
	Items: 1
		0x0000 (OEM-specific)

Handle 0x0026, DMI type 219, 106 bytes
HP ProLiant Information
	Power Features: 0x45010401
	Omega Features: 0x00900002
	Misc. Features: 0x00000000
		iCRU: No
		UEFI: No

Handle 0xFEFF, DMI type 127, 4 bytes
End Of Table
```


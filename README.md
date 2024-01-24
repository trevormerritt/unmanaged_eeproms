# unmanaged_eeproms
Unmanged EEProm dumps

A Collection of dumps from unmanaged switches I own

If these are copied under a copyright, then they belong to whoever owns them.
I am backing up data from my own hardware.

## Use Plan

1. Identify differences in various brands and models of unmanaged switch.
2. Explore Linux DSA options for re-purposing the devices.
3. Something I haven't thought of yet.

## Steps

1. Identify EEPROM
2. Dump EEPROM
3. Compare to possible CPUs for valid configurations? Use CPU data sheet to verify?
4. Update dumped eeprom image and replace on target device to validate findings.
5. **ASSUMING WORKS LIKE BCM ALREADY RESEARCHED** Change bootstrap to SPI slave
6. Attach *something* esp32, esp8266, arduino, raspi, android tv box, whatever to SPI as master and see if it talks.
7. Attach to Linux box (maybe same as step above) and see if we can use the controller.
8. Repeat for next device.

## Switching Silicon Notes

- Broadcom
  - BCM3154
  - BCM3112
  - BCM5315x
  - BCM5316x
  - BCM53106
  - BCM53134
  - BCM53115
  - BCM53128
  - BCM53125
  - BCM5328x
  - BCM53101
  - BCM53202
  - BCM53212
  - BCM53118
  - BCM5395
  - BCM5348
  - BCM53242
- Realtek
  - 

### Serial EEPROM
- Models:
  -  24YXX
    - Y can be LC or C
    - LC = larger pages
    - XX is size in kbit
  -  86YYXX
    - Same as 24YXX for Y
    - XX Table
      - 71 = 1kbit
      - 82 = 2kbit
      - 92 = 4kbit
-  Pins
  - SDA (Data)
  - SCL (Clock)
  - WP (Active High Write Protection)
  - A0, A1, A2 - Address or block select

1. Identify EEPROM on PCB.
  - 24CXX - 2 wire serial
  - 85CXX - 2 wire serial
    - xx is size
      -  
  - 93XXYY
     - YY = size
       - 06 = 265bit(64byte)
       - 46 = 1kbit (128byte)
       - 56 = 2kbit (256byte)
       - 66 = 4kbit (512byte)

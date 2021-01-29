mtd0: 01000000 00010000 "whole flash"
mtd1: 00080000 00010000 "uboot"
mtd2: 00700000 00010000 "kernel0"
mtd3: 00700000 00010000 "kernel1"
mtd4: 00010000 00010000 "others"
mtd5: 00010000 00010000 "parameter tags"
mtd6: 00160000 00010000 "usercfg"


------------------
commands used

./dd-armel-static if=/dev/mtd2 of=/tmp/kernel0.backup
./dd-armel-static if=/dev/mtd3 of=/tmp/kernel1.backup
./dd-armel-static if=/dev/mtd4 of=/tmp/others.backup
./dd-armel-static if=/dev/mtd5 of=/tmp/parametertags.backup
./dd-armel-static if=/dev/mtd6 of=/tmp/usercfg.backup

tftp -p -r wholeflash.backup 192.168.1.232

./dd-armel-static if=/dev/mtd0 of=/tmp/wholeflash.backup
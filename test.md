Books
https://raw.githubusercontent.com/unprovable/PentestHardware/master/DRAFT.pdf



https://www.youtube.com/watch?v=9vsu67uMcko

## Hardware ##

- Basics
- Boot
- UART
- JTAG



Interesting video channel: Make me Hack


1. Information gathering

1.1. Labels on device

1.2. External Sources

    FCC Search Page - YBN
    fccid.io
    fcc.report

1.3. User manual

1.4. Internal Photos

1.5. OSINT

Search engines :

    google.com
    baidu.com
    duckduckgo.com

Forums

    mhhauto.com
    cartechnology.co.uk


2. Disassembly

https://www.youtube.com/watch?v=7v7UaMsgg_c

OSINT Keywords:

    Disassembly / Disassemble
    Teardown
    Open / Opening

3. Component Identification


Source: www.makemehack.com

Video: #01 - Identifying Components - Hardware Hacking Tutorial

Clean components with alcool and afterwards use chalk to highlight the markings/part number on the chips


Datasheets

    https://www.alldatasheet.com/
    https://www.datasheets360.com/
    

4. Pinout Reversing

    Labeled on PCB
    Check the PCB plan on SAP
    Find candidates
    Use a multi-meter

To identify UART or JTAG pins use the Jtagulator.
4.1. Serial Console

Connect using serial console, baud rate 115200

4.2. UART Identification

4.3. JTAG Identification

image2021-3-4_9-42-10.png


5. Connect to Interfaces


6. Retrieve Binaries - Todo


7. Reversing/Fuzzing


8. Exploitation - Todo





FIRMWARE ANALYSIS

1. File

file tries to identify the type of file based on the magic chars

file <filename>


2. Strings

strings shows the strings in a file

strings -n 30 <filename>


3. Hexdump

show the hex and ascii of the file

hexdump -C <filename>


4. Binwalk

binwalk tries to map the files inside a file based on signatures

binwalk -T <filename>


extracts the files

binwalk -e <filename>


shows the file entropy. Closer to 1 means compressed or encrypt

binwalk -E <filename>


5. DD

dd if=<input-filename> of=<output-filename> bs=1024 skip=0 count=1024

bs - block size - 1024 is a good trade off

skip - where to start

count - size of file
6. TAR

Show the contents of a tar file

tar -tvf

Faketoot

fakeroot -s fakeroot.dat unsquashfs -d squashfs-root <filename>

-d - directory

fakroot -i fakeroot.dat bash
7. Extracting the squashfs root file system

To extract the squashfs root file system from the squashfs image we can use the following command:

$ fakeroot -s fakeroot.dat unsquashfs -d squashfs-root u04-sqfs.dat
8. Other tools install


# Install standard extraction utilities

$ sudo apt-get install mtd-utils gzip bzip2 tar arj lhasa p7zip p7zip-full cabextract cramfsswap squashfs-tools sleuthkit default-jdk lzop srecord


# Install sasquatch to extract non-standard SquashFS images

$ sudo apt-get install zlib1g-dev liblzma-dev liblzo2-dev

$ git clone https://github.com/devttys0/sasquatch

$ (cd sasquatch && ./build.sh)


# Install jefferson to extract JFFS2 file systems

$ sudo pip install cstruct

$ git clone https://github.com/sviehb/jefferson

$ (cd jefferson && sudo python setup.py install)


    
    
    
    Dump firmware
Skip to end of metadata

    
Go to start of metadata


--------------------------------------------------

https://www.youtube.com/watch?v=Gh8C2G3qHIw


JTAG/SWD

    Connect via JTAG
    Halt CPU
    Dump Address Space
    Carving Tools to Locate Flash


SPI/I2C Flash

    Connect to Flash with Target Unpowered or Halted
    Dump Flash Memory on Host


NAND/NOR Flash

    Desolder Flash
    Insert into reader
    Dump Flash


Ghidra

openocd

flashrom


https://www.irongeek.com/i.php?page=videos/bsidesindy2017/bsides-indy02-hardware-hacking-abusing-the-things-price-mcdonald

https://securinghardware.com/

https://securinghardware.com/news/Applied-Physical-Attacks-Online-Self-Paced/

https://hardwaresecurity.training/


https://www.irongeek.com/i.php?page=security/hackingillustrated

UART
    


Source: www.makemehack.com

Video: #02 - How To Find The UART Interface - Hardware Hacking Tutorial


If no debug connector is available:

    Check IC - See Datasheet - Find RX and TX
    With Continuity tests find a better place to solder wires



https://en.wikipedia.org/wiki/Serial_port#Speed

    

https://www.gtconsult.com/ProdCon/ProdCon%20-%20Bradley%20Geldenhuys%20-%20Hacking%20IoT%20Devices.pdf    
    
    
    https://conference.hitb.org/hitbsecconf2013kul/materials/D2T3%20-%20Job%20de%20Haas%20-%2020%20Ways%20Past%20Secure%20Boot.pdf

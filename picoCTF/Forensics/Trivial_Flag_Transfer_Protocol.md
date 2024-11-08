# Trivial Flag Transfer Protocol

**Flag:** `picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}`

How you approached the challenge:<br>
This challenge had a network capture file.<br>
These contain data that is passed through a network.<br>
I looked around and found that an application named wireshark can be used to extract data from these.<br>
In wireshark i searched for tftp and exported them all on my system.<br>
I Got 6 files on my system.<br>
3 images in bmp format. A file named `instructions` and a `program.deb` and one named `plan`. instructions had a rot 13 cipher which said `TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN`. <br>
Then as it said i went to the plan then it 
also had a cipher `IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS` and then this message pointed me to the program file.<br>
```bash
╼ $cat plan
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
```
Now i was not sure how to install the program or run it.<br>
after some failed tries i finally installed it.<br>
```bash
user@parrot]─[~/Shared/hi]
└──╼ $./program.deb
bash: ./program.deb: Permission denied
┌─[✗]─[user@parrot]─[~/Shared/hi]
└──╼ $sudo ./program.dbe
sudo: ./program.dbe: command not found
┌─[✗]─[user@parrot]─[~/Shared/hi]
└──╼ $sudo ./program.deb
sudo: ./program.deb: command not found
┌─[✗]─[user@parrot]─[~/Shared/hi]
└──╼ $sudo apt-get install ./program.deb
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'steghide:amd64' instead of './program.deb'
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

The following packages have unmet dependencies:
 steghide:amd64 : Depends: libc6:amd64 (>= 2.2.5) but it is not installable
                  Depends: libgcc1:amd64 (>= 1:4.1.1) but it is not installable
                  Depends: libjpeg62-turbo:amd64 (>= 1:1.3.1) but it is not installable
                  Depends: libmcrypt4:amd64 but it is not installable
                  Depends: libmhash2:amd64 but it is not installable
                  Depends: libstdc++6:amd64 (>= 4.9) but it is not installable
                  Depends: zlib1g:amd64 (>= 1:1.1.4) but it is not installable
E: Unable to correct problems, you have held broken packages.
┌─[✗]─[user@parrot]─[~/Shared/hi]
```
In this i saw an application named steghide which when i researched found that is used to hide info in images and sound files which also matches with our clue.<br>
So `bmp` stands for `Bitmap Image format` which can be used to extract info byn steghide.<br>
Then i got to know how to use steghide
```bash
┌─[✗]─[user@parrot]─[~/Shared/hi]
└──╼ $steghide
steghide version 0.5.1

the first argument must be one of the following:
 embed, --embed          embed data
 extract, --extract      extract data
 info, --info            display information about a cover- or stego-file
   info <filename>       display information about <filename>
 encinfo, --encinfo      display a list of supported encryption algorithms
 version, --version      display version information
 license, --license      display steghide's license
 help, --help            display this usage information

embedding options:
 -ef, --embedfile        select file to be embedded
   -ef <filename>        embed the file <filename>
 -cf, --coverfile        select cover-file
   -cf <filename>        embed into the file <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to embed data
 -sf, --stegofile        select stego file
   -sf <filename>        write result to <filename> instead of cover-file
 -e, --encryption        select encryption parameters
   -e <a>[<m>]|<m>[<a>]  specify an encryption algorithm and/or mode
   -e none               do not encrypt data before embedding
 -z, --compress          compress data before embedding (default)
   -z <l>                 using level <l> (1 best speed...9 best compression)
 -Z, --dontcompress      do not compress data before embedding
 -K, --nochecksum        do not embed crc32 checksum of embedded data
 -N, --dontembedname     do not embed the name of the original file
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

extracting options:
 -sf, --stegofile        select stego file
   -sf <filename>        extract data from <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to extract data
 -xf, --extractfile      select file name for extracted data
   -xf <filename>        write the extracted data to <filename>
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

options for the info command:
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to get info about embedded data

To embed emb.txt in cvr.jpg: steghide embed -cf cvr.jpg -ef emb.txt
To extract embedded data from stg.jpg: steghide extract -sf stg.jpg
```
Then it gave me a file named flag.txt
```bash
[user@parrot]─[~/Shared/hi]
└──╼ $steghide extract -sf ./picture3.bmp -p DUEDILIGENCE
wrote extracted data to "flag.txt".
752674326.316072@[384951462422541] (UTM):* SLSGetNextEventRecordInternal: loc (1193.2, 532.9) conn 0x111007 MouseMoved win 0x5435 (click 1)What you learned through solving this challenge:
```

1. first concep2. second concept
3. etc.

Other incorrect methods you tried:

- a
- b
- c

References

- reference 1
- reference 2
- etc.

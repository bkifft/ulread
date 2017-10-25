### Cloned release notes from initial release notes on Rddit by original author of this application:  
#### https://www.reddit.com/r/amiibros/comments/32fum2/reading_your_amiibo_using_your_computer/  
  
I've seen a total lack of useful applications to read and write NTAG215 as used by amiibos, so I wrote my own application to read them.  
  
Application is provided as source code, with no binaries. It can run everywhere where libnfc is supported, which means Windows, Linux (including Android and Raspberry Pi, amongst others), and Mac. In Windows it can be compiled and used inside the Cygwin POSIX layer.
Source code is here: https://github.com/socram8888/ulread. Grab it using "git clone https://github.com/socram8888/ulread" or downloading it as zip, "cd" to the source, and run "make". If you have libnfc properly configured, just run "./ulread". It will spit some debug information (like tag type, size and UID), and it will then proceed to read all its contents and write them to standard output.
  
For Ubuntu or Debian users:  
  
```
sudo apt-get install build-essential libnfc-dev git --yes
git clone https://github.com/socram8888/ulread/
cd ulread
make
```
And then read them using:
```
export LIBNFC_INTRUSIVE_SCAN=true
./ulread > dump.bin
```
Output is a 1:1 copy of the contents of the NTAG215, except for write-only chunks like write password, which aren't dumped.
If you want to see the contents in hex on your screen directly:
```
export LIBNFC_INTRUSIVE_SCAN=true
./ulread | xxd -g1
```
  
Note it can't yet write them because I don't have any Ultralight tag to test it with, but will be also supported in the near future.


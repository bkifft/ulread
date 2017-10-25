```
## Usage Instructions

Read and Dump ntag215's using:
  
./ulread > dump.bin

Output is a 1:1 copy of the contents of the NTAG215, except for write-only chunks like write password, which aren't dumped. 
If you want to see the contents in hex on your screen directly:

./ulread | xxd -g1

##Compile Instructions:

# For Ubuntu or Debian users:  

sudo apt-get install build-essential libnfc-dev git --yes
git clone https://github.com/socram8888/ulread/
cd ulread
make

# For Windows Users:

###
# Compile "ULREAD" on windows x64
#
# prereq: 	windows x64 compiled version of "libnfc.dll" (see https://github.com/peacepenguin/libnfc-unofficialbuilds)
#			      downloaded extracted "libnfc" source files
#           same prereqs and build environment as for building libnfc in x64 windows:
#           https://github.com/peacepenguin/libnfc-unofficialbuilds/blob/master/README.md
###

# launch mingw64 command line in x64 mode
# copy "libnfc.dll" from c:\windows\system32\libnfc.dll to /mingw64/lib/libnfc.dll    
#  (relative path from within msys-mingw64 shell)
# copy "nfc" directory from extracted "libnfc" source\include\nfc   to  /mingw64/include/nfc 
# install same prereqs and build environment as for building libnfc in x64 windows:
 

# download the ULREAD sources:

# git clone https://github.com/socram8888/ulread.git
# or from:
git clone https://github.com/peacepenguin/ulread.git

cd ulread

mingw32-make.exe 


```

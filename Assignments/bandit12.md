# Bandit Level 12 to 13 Writeup

Author: [Soham Samaddar](https://github.com/CrypthiccCrypto)

Problem Page: [bandit12](https://overthewire.org/bandit/bandit12)

## List of Commands Used
```
ls - used to list files in a directory
file - used to determine the file type
mkdir - used to create a directory
cat - used to read data from a file and give it as output
xxd - used to make a hexdump or do the reverse
cp - used to copy files
mv - used to move/rename files
gzip - used to compress/decompress .gz files
bzip2 - used to compress/decompress .bz2 files
tar - used to compress/decompress .tar files

```

## Walkthrough
The hardest part was realizing that I had to convert the given file to a hexdump using xxd -r. It was relatively smooth sailing afterwards. The only thing left to realise was that I needed to change the names of the files to include the proper extension, but the hint given by the website regarding using mv to change filenames helped to quickly solve this issue.

## Password
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

## Bash/Python script to automate the process
```
mkdir /tmp/sol
cp data.txt /tmp/sol
cd /tmp/sol
xxd -r data.txt 1.gz
gzip -d 1.gz
mv 1 1.bz2
bzip2 -d 1.bz2
mv 1 2.gz
gzip -d 2.gz
mv 2 1.tar
tar -xvf 1.tar
mv data5.bin 2.tar
tar -xvf 2.tar
mv data6.bin 2.bz2
bzip2 -d 2.bz2
mv 2 3.tar
tar -xvf 3.tar
mv data8.bin 69.gz
gzip -d 69.gz
cat 69
```

## Suggested modifications [Optional]
Maybe compress the files many more times so that bruteforcing by hand is not feasible. One needs to write a bash script using a loop to completely decompress the file.

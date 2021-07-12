# microcorruption - Hanoi

Author: [Soham Samaddar](https://github.com/CrypthiccCrypto)

## Password (hexadecimal)
69696969696969696969696969696969a0

## Approach
When I noticed that the input said that the password should be between 8 and 16 characters, I thought it had something to do with overflowing. After playing around for some time:

cmp.b	#0xa0, &0x2410

caught my eye. The password was being stored in the address, 0x2400. So we are comparing the address 16 characters after the password (where the first overflow occurs) directly with the value 0xa0. If it is a success, the door gets unlocked.

Hence the password I input was any set of 16 characters followed by a0.
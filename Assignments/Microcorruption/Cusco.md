# microcorruption - Cusco

Author: [Soham Samaddar](https://github.com/CrypthiccCrypto)

## Password (hexadecimal)
696969696969696969696969696969694644

## Approach
This level took me the longest. 
I knew this level had something to do with overflowing since the password had an 8 to 16 character restriction again. After a long time I noticed:

add	#0x10, sp

which meant that the stack pointer was moving to the first overflow location after the password (at this stage, sp pointed to the start of the password). By default, this address pointed to 443c which was a function to stop program execution. So, by overflowing, I changed this address to 4446 (due to the little endian architecture, I had to input 4644 in the password) which was the unlock_door function. It worked!

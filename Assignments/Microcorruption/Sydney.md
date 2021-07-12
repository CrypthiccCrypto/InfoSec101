# microcorruption - Sydney

Author: [Soham Samaddar](https://github.com/CrypthiccCrypto)

## Password (hexadecimal)
44383c316a363a2b

## Approach
The check_password function was directly checking the password against fixed values at different offsets. The only thing which took me some time to realize was that the architecture was little endian. Hence I had to flip the characters at the time of password input.
# Password Encryption/Decryption with JohnTheRipper

This repository contains instructions for decrypting passwords using JohnTheRipper, a free and open source password cracking tool.

## Decryption with JohnTheRipper

To decrypt a password using JohnTheRipper, follow these steps:

1. Open a terminal and navigate to the directory where the password file is stored.
2. Type `john password.txt` to decrypt the password. JohnTheRipper will automatically detect the format and type of the password and start the decryption process.
3. Once the decryption process is complete, type `john --show password.txt` to display the decrypted password.

## Decryption with a Word List

If you have a word list of possible passwords, you can use JohnTheRipper to decrypt the password as follows:

1. Open a terminal and navigate to the directory where the password file and word list are stored.
2. Type `john --wordlist=/usr/password.txt password.txt`. JohnTheRipper will use the word list to try to decrypt the password.

## Decryption with OpenMP

If you want to speed up the decryption process, you can use OpenMP to open multiple processing units. This is particularly useful when working with clusters. To decrypt the password using OpenMP, follow these steps:

1. Open a terminal and navigate to the directory where the password file is stored.
2. Type `john --fork 4 password.txt`. JohnTheRipper will use OpenMP to open four processing units and decrypt the password.
3. 
## Decryption with Mask

If you have a pattern for the password, you can use a mask to try to decrypt the password. For example, if you know that the password starts with "TheNetPassword" and ends with four digits, you can use the following mask:

```sh
john --mask="TheNetPassword[0-9]{4}" password.txt
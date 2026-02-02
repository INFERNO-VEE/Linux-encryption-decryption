# Project 1 – Linux Encryption & Decryption

## Objective
This project demonstrates how file encryption and decryption work on a Linux system using OpenSSL.
It shows how encryption protects data confidentiality but does not secure a system by itself.

## Tools Used
- Linux Terminal
- OpenSSL
- AES-256-CBC encryption

## Step 1: Create a Plaintext File
echo "Encryption hides data but does not make systems secure." > message.txt
cat message.txt

## Step 2: Encrypt the File
openssl enc -aes-256-cbc -salt -in message.txt -out message.enc
### Password Prompt
When running the encryption command, OpenSSL will prompt for a password:
- Enter encryption password
- Verify encryption password
This password is used to derive the encryption key. The password is never displayed or stored in the command. Without the correct password, the encrypted file cannot be decrypted.

## Step 3: Verify Encrypted Content
cat message.enc (The output appears unreadable, which means that the encryption was successful)

## Step 4: Delete the original file
rm message.txt

## Step 5: Decrypt the File
openssl enc -d -aes-256-cbc -in message.enc -out message_decrypted.txt
cat message_decrypted.txt
### Password Requirement
During decryption, OpenSSL prompts for the same password used during encryption.
If the password is incorrect, decryption will fail.

## Some keypoints to take note of;
-Encryption protects data confidentiality
-Anyone with the coreect password can decrypt the data
-Encryption alone does not secure systems 
-Strong passwords and access control are critical

## Lab Evidence 
The screenshot below shows the encryption and decryption process performed in the Linux terminal

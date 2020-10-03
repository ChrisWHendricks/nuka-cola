# Creating an Encrypted Password file.

All of the following steps were performed on a Linux machine 

Create plain text file with the desired password

```echo CrashOverride > mypass```

Next using openSsl encrypt the password file
```openssl enc -aes256 -pbkdf2 -salt -in mypass -out mypass.enc```

After executing the above command you will be prompted to enter a AES Encryption password (This does not need to be the same as the password in your text file) 
For this example I used the password 'password' as the encryption password, whereas the password in the text file is CrashOverride

If I print out the file we can see that it is encrypted

```
$ cat mypass.enc
Salted__�^�rW�jN��56�I��<�SO��
```
We can Decrypt the password by using the following command 

`openssl enc -aes256 -pbkdf2 -salt -d -in mypass.enc`  
After verifying this I deleted the plain text mypass file.

## Creating Self-Signed Certificate








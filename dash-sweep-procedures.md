Dash Paper Wallet Sweep Procedures v1.0
=======================================

The latest version of this document is available at https://github.com/rstms/paper-wallet-procedures/blob/master/dash-sweep-procedures.md
For further information please contact the author via github.

Install Barcode To PC Server
----------------------------
On your desktop, go to https://barcodetopc.com/ and install the server program.


Install Barcode To PC Phone App
-------------------------------
On your phone, go to the browser and open https://barcodetopc.com, then use the links to the Play store or the App store to install the app


Install Dash Wallet on Desktop Windows System
-------------------------------------------------
### Install the Dash Wallet Software from www.dash.org
As of 2017-04-06, the latest Dash Core version for a Windows 10 PC is:
https://www.dash.org/binaries/dashcore-0.12.1.4-win64-setup.exe

Install and run the program

### Use Default Install Directories:
 - Wallet Program: ```C:\Program Files\Mist```
 - Wallet Data: ```C:\Users\[USER_NAME]\AppData\Roaming\Ethereum```

Once the program is started, add an account.  Record the password.

### Open the geth command line environment
Open a command prompt and issue these commands:
```
cd %APPDATA%\mist\binaries\geth\unpacked
dir
```
Verify the output looks similar to this:
```
Volume in drive C has no label.
 Volume Serial Number is 88E5-8A20

 Directory of C:\Users\mkrueger\AppData\Roaming\Mist\binaries\Geth\unpacked

04/06/2017  11:09 AM    <DIR>          .
04/06/2017  11:09 AM    <DIR>          ..
04/06/2017  11:09 AM    <DIR>          geth-windows-amd64-1.5.9-a07539fb
04/06/2017  11:09 AM        20,146,700 geth.exe
               1 File(s)     20,146,700 bytes
               3 Dir(s)  662,984,704,000 bytes free
```

Command:
```
geth account list
```

Should produce output similar to this: (the libusb error is normal)
```
C:\Users\mkrueger\AppData\Roaming\Mist\binaries\Geth\unpacked>geth account list
I0406 11:32:02.754257 node/config.go:445] Failed to start Ledger hub, disabling: libusb: not found [code -5]
Account #0: {814559b18572db0a37a1cb26e1aff43913c63401} keystore://C:\Users\mkrueger\AppData\Roaming\Ethereum\keystore\UTC--2017-04-06T16-11-05.088322700Z--814559b18572db0a37a1cb26e1aff43913c63401
```
The address above {inside curly braces} should match the one created as the first account and displayed in the mist application.


### Sweep Paper Wallet
Copy your paper wallet private key to the local file private.txt

Command: 
```
notepad private.txt
```
Position the cursor in the open notepad edit window.

Type or use the “Barcode To PC” application to enter the desired private key sequence.

Save and close notepad

Command:
```
type private.txt
```

Verify that the contents of the file match the paper wallet private key.

Generate a password for the swept key account.  Record it – you will need it to use the account in Mist.

Command:
```
geth wallet import private.txt
```
You will need to enter your password (twice)

Output should look something like this:
```
C:\Users\mkrueger\AppData\Roaming\Mist\binaries\Geth\unpacked>geth account import private.txt
I0406 12:02:07.744496 node/config.go:445] Failed to start Ledger hub, disabling: libusb: not found [code -5]
Your new account is locked with a password. Please give a password. Do not forget this password.
Passphrase:
Repeat passphrase:
Address: {4b758fadc1fa40a22829bed488f043fdeea8c66d}
```
Note:  the libusb error is a known issue and not a problem.
Verify that the address displayed in curly braces matches the ETH PUBLIC ADDRESS on your paper wallet.

Sweep Operation Complete
------------------------
Verify that a new account with your paper wallet address is now displayed with the correct value in Mist.
Select the account with the address matching your paper wallet public address.  You can now use the password to initiate a spend transaction.

Note: If you've just installed Mist, you may have to wait for the blockchain data to be downloaded before the correct value is shown for your account.  For immediate verification, you can use a blockchain explorer like https://etherchain.org
